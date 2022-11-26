
## C#初级编程笔记
```
如果将某个变量进行public修饰，则可在脚本中直接修改变量。如果不加修饰，默认为private。比如在a脚本中声明public a，则在b函数中可以使用private a来调用a中的函数或者变量，需声明xx = new a（）；
dowhile循环不管如何，都将调用一次。
Awake在脚本未被使用时即调用，比如分配给敌人的子弹，Start在被使用时调用，比如子弹的射击
非物理对象得移动，简单的计时器，按键输入检测使用Update。但由于每一帧的处理时间不同，Update的时间间隔不同。因此，任何影响刚体，即物理对象的动作都应该使用FixedUpdate，使用AddForce
在 FixedUpdate 内应用运动计算时，无需将值乘以 Time.deltaTime。这是因为 FixedUpdate 的调用基于可靠的计时器（独立于帧率）。
Ctrl+shift+M启用函数调用界面
Unity采用左手坐标系，Vector3.Cross(VectorA,VectorB)用于计算叉积，比如用于扭转炮台，确定围绕娜个轴施加扭矩，假设已知炮台目前的朝向，也知道炮台的目标朝向，就可以对两个向量进行叉积运算，确定对
哪个轴施加转动扭矩。Vector3.magnitude用于计算点积，比如飞机点积为0，说明阻力最小，如果为正值，说明飞机朝上，应施加阻力。
myLight.enabled = false；myLight.enabled = !myLight.enabled;用于设为非当前值，也可用于禁用脚本。
gameObject.SetActive(false);禁用游戏物体。myObject.activeSelf查询物体激活状态，"Active Self: "激活。Active in Hierarchy" + myObject.activeInHierarchy用于激活父类。
public float moveSpeed = 10f;transform.Translate(Vector3.forward * moveSpeed * Time.deltaTime);移动
public float turnSpeed = 50f; transform.Rotate(Vector3.up, turnSpeed * Time.deltaTime);旋转
public Transform target;
    
    void Update ()
    {
        transform.LookAt(target);
    }
看向目标的坐标；
```
## MonoBehavior生命周期笔记
> Start - 在游戏对象开始存在时（加载场景或实例化游戏对象时）调用。   
> Update - 每帧都会被调用。    
> FixedUpdate - 每个物理时间步进调用。    
## 思考题：
``` C#
    public class HpBuff: Buff
    {
    public float DeltaHp=1;
    public HpBuff(Player player, BuffKind buffKind, float length) : base(player, buffKind, length){}
    public override void OnAdd()
    {
        base.OnAdd();
        m_Player.Hp += DeltaHp;
    }

    }
```
## 回答
1. 你的自我介绍
   > 大家好!我是来自物联网2202的张智林，很高兴来到Gamecore游戏工作室，与大家共同学习游戏开发，期待与大家共同进步，携手做出一款属于自己的好游戏<(￣︶￣)↗[GO!]    
2. 你最喜欢的游戏类型和一款游戏，以及原因    
   > 只要是好玩的游戏什么类型都可以
3. 回答Unity中有哪些生命周期函数，它们各自在什么时候调用
   > 见上方MonoBehavior生命周期笔记   
4. 你本周的基础知识学习笔记
   > 见上方笔记
``` Markdown
