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

然后给 cube 加上物理属性，否则 gripper 会直接穿过它：

选中 cube → 右边 Property 面板 → **+Add → Physics → Colliders Preset**
<img width="782" height="809" alt="image" src="https://github.com/user-attachments/assets/bf9c4ffd-db6b-4153-a26a-055d106cd701" />

---

## 第四步：控制 Gripper

**Tools → Physics → Physics Inspector**

在 Stage 树里选顶层的 robot prim（`so101_new_calib`），然后点 Physics Inspector 里的**刷新按钮（圆圈箭头）**，就能看到所有 joint 的 slider。
<img width="2539" height="989" alt="image" src="https://github.com/user-attachments/assets/7f32b15a-6bc1-403b-9f7e-03196b9a1387" />


按 **▶ Play**，然后：

1. 用各个 joint slider 把 arm 摆到 cube 上方
2. 把 `gripper` slider 拉到最大（完全打开）
3. 慢慢移动 arm 到 cube 两侧
4. 把 `gripper` slider 拉到最小（闭合）
5. 抬起 arm，看 cube 会不会跟着走
![Gripper Test Demo](https://github.com/Jeffaaay/isaac-sim-tutorial/blob/main/demo.gif?raw=true)
---

## 结论：gripper 测试结果

两个 finger 接触面太小，对硬质 cube 摩擦力不够，很难稳定夹起。

**这不是 RL 或者代码的问题，是 gripper 几何形状的物理限制。**

对于需要可靠抓取硬质物体（比如围棋棋子）的场景，**吸盘（suction cup）是更好的选择**。
