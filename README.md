# rime-ice-customized

根据自己的习惯修改的 rime-ice

我需要一个词库词汇量巨大的输入法，所以除了 Dvel 大佬的词库，还有一个贴吧找的词库。

# 使用方法

1. 下载 Dvel 大佬的 [rime-ice](https://github.com/iDvel/rime-ice) 放在 `%APPDATA%\Rime` 文件夹下。
2. 下载本项目覆盖之，后重新部署。
3. 不需要其他词库，则下载后删除下列名称开头的‘.dict.yaml’词库文件。
   - luna_pinyin
   - super_rime
   - easy_en

# 更新记录

## 2023-09-14

- 添加简陋的星露谷物语词库，~~AI自动补全真好用，自动补全编码。~~
- 调整两个词条到别的词库中，
- 调整Dota2搜狗词库到单独的SG词库文件夹，
- 添加搜狗 网络流行新词 词库。

## 2023-09-01 

修正词库文件名的错误，词库文件改名，`dict.yaml`中内没更正，导致rime部署出现问题。
   - 如果`rime_ice.dict.yaml`引用了不存在的词库，那么在这个词库下的其他词库会被略过。

## 2023-08-29

同步`rime-ice`的 Lua 文件，同步`emoji`文件夹，启用强制删词、隐藏候选词功能。

删除或者说隐藏了一个候选词，因为难以确认这个候选词来自那个词库。

**rime.lua**
```Lua
词条隐藏、降频
在 engine/processors 增加 - lua_processor@cold_word_drop_processor
在 engine/filters 增加 - lua_filter@cold_word_drop_filter
在 key_binder 增加快捷键：
turn_down_cand: "Control+j"  # 匹配当前输入码后隐藏指定的候选字词 或候选词条放到第四候选位置
drop_cand: "Control+d"       # 强制删词, 无视输入的编码
```
调整`Control+j`的词条位置到 10 ，也就是翻页后的第一位。

## 2023-08-15

更新了几次，但忘了写日志。

1. 下载搜狗词库，转换后手动整理，并添加了Minecraft词库。

2. 使用 custom 对rime-ice进行修改。

3. 候选词个数 10 。

4. 调整了几个词库的词条位置。

5. `custom_phrase.txt`添加三个词条并测试如何固定候选词位置。在自定义短语txt文件中添加，并从高到低设置权重。

## 2023-06-28

尝试模仿大佬的操作,结果是自己理解不能的错误,更新了`weasel.custom`的文件内容结构,其他没变.

## 2023/06/21

出现`ctrl+。`切换标点，提示框看不到`，。|,.`的问题，以rime西米的默认配色为底，修改仿win10配色方案。

只有候选词部分，强烈建议开启输入字符光标处内嵌

```
"style/inline_preedit": true
```

![插图1](custom_dict/仿win10配色.jpg)

## 2023/06/08

仿Win10配色,简单仿一下布局,不喜欢圆角,所以调成了方角,输入字符光标处内嵌,字号16

## 2023/06/04 

新建并引用一个新词库,Dota2英雄别名词库,在custom_dict\Dota2_YX.dict.yaml文件.

打开 Tab 切换拼音功能.

## 2023/05/05

统一使用 `custom`进行修改,注释掉两个词库,使用右Shift切换中英.

## 2023/05/06

替换了方案选单中,Emoji选项的显示符号,💀😀-->❌⭕  

## 2023/05/12  

`custom_phrase.txt` 添加几个词条.  

# 修改项

有点过时，有时间再改。

~~暂时想不起来全部,先写一部分.~~

1. 永久记住 中英符号、全半角、简繁等。手动注释 `rime_ice.schema.yaml`文件中 `switches`项中的`reset`。
2. 默认不在候选词中添加Emoji。
3. 合并了一个8-9年前的700万明月拼音的词库进去,
4. 拆分 `luna_pinyin.sgmain.dict.yaml`词库，它导致rime部署时间过长。
   - 如果经常需要重新部署，就算你需要大量词库词汇，也不建议你添加这个词库。
   - 部署时间过长，导致没办法从部署时间上判断，自己的修改是否存在问题。
   - 还是有很多问题，干脆放弃了，这个最大的词库。
5. 添加一个自己的词库，作为自定义短语的词库。但应该不会传上来。
   - 笔记：权重 `weight`数字越大，候选词中排位约靠前。
6. 候选词 9 个。
7. 使用 [霞鹜文楷](https://github.com/lxgw/LxgwWenKai) 作为rime的字体。因为它能显示𰻝𰻝面的𰻝（biang）。
8. 方案选单只使用 `Control+grave`。
9. 使用pgup、pgdn，候选词翻页。也不知道生效没。
10. 右shift，切换中英。方便一些需要英文输入又频繁使用Shift的游戏。特别是某些沙盒生存建造游戏。
11. `ctrl+。`，切换中英符号。
12. ~~ctrl+shift+f，切换简繁。~~ 此项无效
13. `Shift+space`，切换全半角。
    ~~应该没有了~~。

# 致谢

感谢 [Dvel](https://github.com/iDvel) 大佬的 [rime-ice](https://github.com/iDvel/rime-ice)

感谢 [戶下之羽](https://github.com/Chernfalin) 大佬的["SuperRime拓展词库 for 朙月拼音(700万词-含BetterRime) v20.3"](https://github.com/Chernfalin/SuperRimeDict) 词库。

感谢 [rime西米](https://fxliang.github.io/RimeSeeMe/) ，用这个网站做的皮肤。