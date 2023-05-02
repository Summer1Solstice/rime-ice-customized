# rime-ice-customized
根据自己的习惯修改的 rime-ice  
我需要一个词库词汇量巨大的输入法，所以除了 iDvel 大佬的词库，还有一个贴吧找的词库。

# 使用方法
下载 iDvel 大佬的 [rime-ice](https://github.com/iDvel/rime-ice) 放在 `%APPDATA%\Rime` 文件夹下。  
下载本项目覆盖之  
不需要词库，则下载后删除‘luna_pinyin’开头的‘.dict.yaml’。

# 
# 修改项
暂时想不起来全部,先写一部分.

1. 永久记住 中英符号、全半角、简繁等。
2. 合并了一个8-9年前的700万明月拼音的词库进去,
3. 拆分luna_pinyin一个比较大的词库，它导致rime部署时间过长。
    - 如果经常需要重新部署，就算你需要大量词库词汇，也不建议你添加这个词库。
    - 部署时间过长，导致没办法从部署时间上判断，自己的修改是否存在问题。
    - 还是有很多问题，干脆放弃了，其中一个最大的词库。另外,发现小狼毫只有32位。
4. 添加一个自己的词库，作为自定义短语的词库。但应该不会传上来。  
    - 笔记：权重`weight`数字越大，候选词中排位约靠前。
5. 候选词 9 个。
6. 使用 [霞鹜文楷](https://github.com/lxgw/LxgwWenKai) 作为rime的字体。因为它能显示𰻝𰻝面的𰻝（biang）。
7. 方案选单只使用 Control+grave。
8. 使用pgup、pgdn，候选词翻页。也不知道生效没。
9. shift切换中英
10. ctrl+。，切换中英符号。
11. ctrl+shift+f，切换简繁。
12. Shift+space，切换全半角。
应该没有了。

# 致谢
感谢 iDvel 大佬的 [rime-ice](https://github.com/iDvel/rime-ice)
感谢 "SuperRime拓展词库 for 朙月拼音(700万词-含BetterRime) v20.3" 词库。
