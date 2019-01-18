#matplotlib库不能缺省
import jieba
import wordcloud
f = open("a.txt", "r", encoding="utf-8")

t = f.read()
f.close()
ls = jieba.lcut_for_search(t)
txt = " ".join(ls)

txt = txt.replace("装置","")
txt = txt.replace("研究","")
txt = txt.replace("一种","")

w = wordcloud.WordCloud( \
    width = 1000, height = 700,\
    background_color = "white",
    font_path = "msyh.ttc"    
    )
w.generate(txt)
w.to_file("青少年科技创新大赛词云最优版.png")

