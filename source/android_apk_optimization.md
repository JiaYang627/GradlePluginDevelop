###apk瘦身

- 1.使用一套图资源

对于绝大对数APP来说，只需要取一套设计图就足够了。鉴于现在分辨率的趋势，建议取720p的资源，放到xhdpi目录。

相对于多套资源，只使用720P的一套资源，在视觉上差别不大，很多大公司的产品也是如此，但却能显著的减少资源占用大小，顺便也能减轻设计师的出图工作量了

- 2.开启minifyEnabled混淆代码

- 3.开启shrinkResources去除无用资源

- 4.删除无用的语言资源（大多数情况仅仅需要中文）

         android{
             defaultConfig{
                 resConfigs "zh"
             }
         }
         
- 5.使用tinypng有损压缩

    android打包本身会对png进行无损压缩，所以使用像tinypng这样的有损压缩是有必要的。 重点是Tinypng使用智能有损压缩技术，以尽量少的失真换来图片大小的锐减，效果非常好，强烈推荐。
    
    Tinypng的官方网站：http://tinypng.com/ 拖进去就可以
    
- 6.对于非透明的大图使用jpg格式
     jpg将会比png的大小有显著的优势，虽然不是绝对的，但是通常会减小到一半都不止。在启动页，活动页等之类的大图展示区采用jpg将是非常明智的选择。
     
- 7.使用webp格式（系统版本需要兼容）
  
  webp支持透明度，压缩比比jpg更高但显示效果却不输于jpg，官方评测quality参数等于75均衡最佳。
  
  相对于jpg、png，webp作为一种新的图片格式，限于android的支持情况暂时还没用在手机端广泛应用起来。从Android 4.0+开始原生支持，但是不支持包含透明度，直到Android 4.2.1+才支持显示含透明度的webp，使用的时候要特别注意。
  
  官方介绍：https://developers.google.com/speed/webp/docs/precompiled
  
- 8.shape替换一些背景

- 9.selector 处理不同颜色图片使用着色方案

- 10.覆盖第三方库里的大图1x1

  有些第三方库引用了一些大图,但实际上并不会并我们用到，第三方的图片通常会拷贝到我的项目中，因此我们可以使用同名1X1像素透明图片进行覆盖

- 11.第三方库避免重复引用

- 12.在线资源应用

- 13.插件化

- 14.删除armable-v7下so

- 15.使用7z极限压缩图片