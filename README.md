# Isaac Sim 机械臂测试教程

## 第一步：加载机械臂

打开 Isaac Sim，然后：

**File → Open → 选择你的 robot USD 文件**

![robot loaded](https://github.com/user-attachments/assets/12ec1fed-f284-4bef-80e3-0c5c7138301c)
![robot view](https://github.com/user-attachments/assets/3e9d2193-9fe9-4662-b3a5-9e81a664e24b)

---

## 第二步：添加地面

没有地面的话物体会掉进虚空：

**Create → Physics → Ground Plane**

---

## 第三步：添加 Cube

**Create → Shapes → Cube**

在右边 Property 面板设置：

| 参数 | 值 |
|------|----|
| Scale X/Y/Z | 0.03, 0.03, 0.03（3cm）|
| Translate X | 0.2 |
| Translate Y | 0.0 |
| Translate Z | 0.015 |

![cube property](https://github.com/user-attachments/assets/ad85ba44-1fbb-4c8f-9b80-f84281f6b868)
![cube in scene](https://github.com/user-attachments/assets/2eefcac0-0627-4b7d-9f4a-a0a41fc48b5a)

---

## 第四步：控制 Gripper

**Window → Articulation Inspector**

按 ▶ Play，然后拖动 gripper joint slider 测试开合。
