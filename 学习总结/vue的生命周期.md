## vue的生命周期

1.beforeCreate 初始化实例后 数据观测和数据配置之前调用

2.created 实例创建完成后调用

3.beforeMount 挂在前开始调用

4.mounted el被新建 vm.$el 替换并挂在到实例上之后调用

5.beforeUpdate 数据更新时调用

6.updated 数据更改导致的 DOM 重新渲染后调用

7.beforeDestroy 实例被销毁前调用

8.destroyed 实例销毁后被调用