# 使用Python 3.9官方基础镜像
FROM python:3.9

# 创建工作目录
WORKDIR /app

# 确保所需目录存在，并复制 gz 文件
RUN mkdir -p /app/data

COPY BPIC12.xes.gz /app/data/BPIC12.xes.gz
COPY BPIC13_cp.xes.gz /app/data/BPIC13_cp.xes.gz
COPY BPIC13_i.xes.gz /app/data/BPIC13_i.xes.gz
COPY BPIC14_f.xes.gz /app/data/BPIC14_f.xes.gz
COPY BPIC15_1f.xes.gz /app/data/BPIC15_1f.xes.gz
COPY BPIC15_2f.xes.gz /app/data/BPIC15_2f.xes.gz
COPY BPIC15_3f.xes.gz /app/data/BPIC15_3f.xes.gz
COPY BPIC15_4f.xes.gz /app/data/BPIC15_4f.xes.gz
COPY BPIC15_5f.xes.gz /app/data/BPIC15_5f.xes.gz
COPY BPIC17_f.xes.gz /app/data/BPIC17_f.xes.gz
COPY RTFMP.xes.gz /app/data/RTFMP.xes.gz
COPY SEPSIS.xes.gz /app/data/SEPSIS.xes.gz
COPY algorithm.py /app/algorithm.py

# 使用 && 合并指令，减少层数，安装所需依赖并解压文件
RUN apt-get update && \
    apt-get install -y gzip && \
    gzip -d /app/data/BPIC12.xes.gz && \
    gzip -d /app/data/BPIC13_cp.xes.gz && \
    gzip -d /app/data/BPIC13_i.xes.gz && \
    gzip -d /app/data/BPIC14_f.xes.gz && \
    gzip -d /app/data/BPIC15_1f.xes.gz && \
    gzip -d /app/data/BPIC15_2f.xes.gz && \
    gzip -d /app/data/BPIC15_3f.xes.gz && \
    gzip -d /app/data/BPIC15_4f.xes.gz && \
    gzip -d /app/data/BPIC15_5f.xes.gz && \
    gzip -d /app/data/BPIC17_f.xes.gz && \
    gzip -d /app/data/RTFMP.xes.gz && \
    gzip -d /app/data/SEPSIS.xes.gz && \
    ls -la /app && ls -la /app/data &&\
    pip install pm4py
