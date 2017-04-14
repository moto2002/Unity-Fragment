# Unity-Fragment
用于UGUI界面间的跳转 类似Android中的Fragment

build in Unity 5.3.4f

## 用法
1.FragmentManager挂在Canvas上

2.每个界面的根物体上挂继承Fragment的实现脚本

## Fragment
**Fragment中包含生命周期的回调：**

OnEnterStack：fragment进栈时回调 可以用于实现与OnEnable不同的逻辑

OnExitStack：fragment出栈时回调 可以用于实现与OnDisable不同的逻辑

OnIntent：通过FragmentIntent启动fragment时回调 可用于界面跳转时传些数据

DoExitAnimation：可以在这里实现界面退出动画

DoEnterAnimation：可以在这里实现界面进入动画

OnDynamicInstantiated：fragment动态加载时回调




**Fragment中包含按键时间的回调**

OnBackPressed：按返回键时回调

OnMenuPressed：按菜单键时回调

OnHomePressed：按Home键时回调

OnLongBackPressed：长按返回键时回调

## FragmentManager

**支持两种形式的Fragment**

静态Fragment：在Scene中已经存在的物体上继承Fragment的实现脚本，第一个可见物体上的Fragment被认为是默认显示的界面。

动态Fragment：在编辑器中的FragmentManager脚本上配置界面的任意个Prefab，每个Prefab认为是一个界面，初始化时需要手动显示默认显示的界面。需要再TagManager中添加名为“UnInstantiateFragment”的tag

**支持多种Fragment启动模式**

效果与安卓中activity启动模式一样

FLAG_NEW_INSTANCE：以一个新的Fragment实例启动

FLAG_CLEAR_TOP：若栈中存在该Fragment实例 则将栈顶的其他Fragment实例都清空 并将该Fragment实例置顶并显示

FLAG_SINGLE_INSTANCE：若栈中存在该Fragment实例 则将该Fragment实例置顶并显示


## License

MIT License

Copyright (c) 2017 Hcq

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
