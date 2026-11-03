[Uploading hhh.py…]()
import random #导入随机模块

levels=['INFO','WARNING','ERROR']
msgs=[
    '用户登录成功',
    '数据库连接超时',
    '缓存未命中',
    '接口返回 500',
    '任务执行完成',
    '配置加载失败'
]
with open('sample.log','w',encoding='utf-8') as f:
    for i in range(1,51):
        lv=random.choice(levels)  #把levels中的元素随机一个分配到lv
        msg=random.choice(msgs)   #把msgs中的元素随机一个分配到msg
        f.write(f'2026-11-02 14:{i:02d}:00[{lv}]{msg}\n')  #for循环遍历取值，i:02d(01--02--03...),然后再把lv和msg随机的数据引进并换行
print('已生成 sample.log')
#注释：02d： 格式化输出,d代表整数,02意思：占两个字符宽数，不够2位，前面补0.例如：
n=5
print(f'{n:02d}') #05  (如果n=12的话，那么前面就不加0)
# import random:导入随机模块
# random.choice():括号内的数据(levels)随机挑一个赋予变量lv


total = 0
i1 = 0
w1 = 0
e1 = 0
with open('sample.log','r',encoding='utf-8') as f:
    for i in f:
        total+=1
        i=i.strip()
        level=i.split('[')[1].split(']')[0]
        if level=='INFO':
            i1+=1
        elif level=='WARNING':
            w1+=1
        elif level=='ERROR':
            e1+=1
print(f'总行数:{total}')
print(f'INFO:{i1}')
print(f'WARNING:{w1}')
print(f'ERROR:{e1}')

with open('sample.log','r',encoding='utf-8') as old_f,open('report.txt','w',encoding='utf-8') as f:
    print(f'->共{e1}条ERROR:')
    for line in old_f:
        line=line.strip()
        lv=line.split('[')[1].split(']')[0]
        if lv == 'ERROR':
            f.write(f'{line}\n')
            print(f'->{line}')
print('->报告已写入report.txt')

import os
print(os.getcwd())




#
# import random
# levels=['INFO','WARNING','ERROR']
# mags=['问题1',
#       '问题2',
#       '问题3',
#       '问题4',
#       '问题5',
#       '问题6']
#
# with open('test1.txt','w',encoding='utf-8') as f:
#     for i in range(1,51):
#         level=random.choice(levels)
#         mag=random.choice(mags)
#         f.write(f'2026-11.3-0:{i:02d}:00:[{level}],{mag}\n')
#
# total=0
# i1=0
# w1=0
# e1=0
# with open('test1.txt','r',encoding='utf-8')  as f:
#     for line in f:
#         total+=1
#         line=line.strip()
#         lv=line.split('[')[1].split(']')[0]
#         if 'INFO' in lv:
#             i1+=1
#         elif 'WARNING' in lv:
#             w1+=1
#         elif 'ERROR' in lv:
#             e1+=1
#     print('日志已写入报告：')
#     print(f'一共{total}条程序')
#     print(f'一共{i1}条INFO')
#     print(f'一共{w1}条WARNING')
#     print(f'一共{e1}条ERROR')
# with open('test1.txt','r',encoding='utf-8') as old_f,open ('tohka.txt','w',encoding='utf-8') as f:
#     print(f'共{e1}条ERROR:')
#     for i in old_f:
#         i=i.strip()
#         if 'ERROR' in i:
#             print(i)
#             f.write(f'{i}\n')
#     print('报告已写入thoka')
#
#
#
#
# a='sjdnandad'
# b=a.replace('sjdn','sdaawdaw')
# print(b)
# print(a)































