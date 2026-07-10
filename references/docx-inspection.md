# .docx 文件深度检测指南

## 使用场景
当 `read_file` 返回 `"Cannot read binary file"` 或 python-docx 提取到空内容时，
需要确认该 .docx 是真正的文本文档还是图片嵌入。

## 快速检查：是否为图片嵌入

```python
import zipfile
docx_path = "/path/to/file.docx"
with zipfile.ZipFile(docx_path) as z:
    names = z.namelist()
    print(names)
    # 如果只有 word/media/image*.png 无文本 -> 图片嵌入
    has_images = any('media/image' in n for n in names)
    has_text = any(n == 'word/document.xml' for n in names)
    print(f"Has images: {has_images}, Has document.xml: {has_text}")
```

## 完整提取脚本

```python
from lxml import etree
import zipfile

docx_path = "/root/workplace/简历.docx"

with zipfile.ZipFile(docx_path) as z:
    # 检查 ZIP 结构
    for name in z.namelist():
        print(name)
    
    # 提取 document.xml 中的文本
    with z.open("word/document.xml") as f:
        xml = f.read()
    
    root = etree.fromstring(xml)
    
    # 普通段落文本
    for t in root.iter('{http://schemas.openxmlformats.org/wordprocessingml/2006/main}t'):
        if t.text and t.text.strip():
            print(t.text.strip())
    
    # DrawingML 文本框中的文本
    for t in root.iter('{http://schemas.openxmlformats.org/drawingml/2006/main}t'):
        if t.text and t.text.strip():
            print(t.text.strip())
```

## 已知的 9p 挂载架构（Docker 后端）

| 容器路径 | 对应 Windows 路径 |
|---------|------------------|
| `/root` | `C:\Users\{USER}\AppData\Local\hermes\sandboxes\docker\default\home` |
| `/workspace` | `C:\Users\{USER}\AppData\Local\hermes\sandboxes\docker\default\workspace` |
| `/root/.hermes/skills` | `C:\Users\{USER}\AppData\Local\hermes\skills` (只读) |
| `/root/.hermes/cache/documents` | `C:\Users\{USER}\AppData\Local\hermes\cache\documents` (只读) |

**桌面文件** (`C:\Users\{USER}\Desktop\`) 不在任何挂载点中，不可直接访问。
解决方案：让用户将文件复制到 `C:\Users\{USER}\AppData\Local\hermes\sandboxes\docker\default\home\`，
容器内路径即为 `/root/文件名`。
