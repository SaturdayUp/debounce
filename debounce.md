# debounce
防抖函数

//防抖函数
export function debounce(func,delay){
  //定义一个定时器，并初始化为null
  let timer=null
  //返回一个函数，可以传入多个参数
  return function (...args){
    //如果当前定时器不为空，那么清空当前定时器
    if (timer) clearTimeout(timer)
    //重新设置定时器，重新开始计时
    timer=setTimeout(()=>{
      func.apply(this,args)
    },delay)
  }
}
