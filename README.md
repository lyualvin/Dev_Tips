# Dev_Tips
开发过程中的提醒、建议、思考等

复用不是复制，当需要通过复制相同代码来扩展功能时，考虑继承、MonoBehaviour或者Component来实现

工作项目遇到了一个System.GC.Collect()的坑，编辑器版本是2021.3.17f1，在顶栏设置Jobs->Burst->Enable Compilation，当开启后，GC.Collect()的耗时会来到300ms以上(可能和项目大小有关)，此时无论在编辑器下还是运行时调用GC.Collect()都会有高耗时，关闭该选项然后重启编辑器即可恢复。

官方文档中提到Animator和UI结合使用时，即便当前没有正在播放的动画，节点的Canvas也会每一帧都Rebuild，使用Animation或者DoTween可以优化，或者播放完动画后禁用Animator。
(文档来自官方blog 《Get over 80 tips to speed up in Unity with our latest productivity e-book》)
