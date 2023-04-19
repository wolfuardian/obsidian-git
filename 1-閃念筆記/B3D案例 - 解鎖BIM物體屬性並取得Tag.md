```python
import bpy
import os
os.system('cls')
# 獲取當前選定的物體
selected_objects = bpy.context.selected_objects

# 遍歷選定的物體
for obj in selected_objects:
    if obj.type != 'MESH':
        continue
    bpy.ops.bim.enable_editing_attributes(obj=obj.name, obj_type="Object")
    bpy.ops.bim.disable_editing_attributes(obj=obj.name, obj_type="Object")
    tag = obj.BIMAttributeProperties.attributes['Tag'].string_value
    print(f"\nID (tag)：{tag}")
    print(f"\n")
```
