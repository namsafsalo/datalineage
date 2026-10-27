# datalineage

**追踪数据集版本的演变与来源改动。**

`datalineage` —— 沿版本链记录每次变更的内容、原因与影响范围

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`datalineage.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install namsafsalo-datalineage
```

装完直接用命令名调用：

```bash
datalineage --help
```

也可以不用安装，直接把 `datalineage.py` 拷走用——它只依赖标准库。

## 为什么需要它

谱系要能定位到具体哪次改动引入了某个问题

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 数据版本谱系 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python datalineage.py --file input.txt
python datalineage.py --text "示例内容"
python datalineage.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 计数按字面 token 统计，不做词形还原。
- 只报告分布，不判断该保留哪些。

## 跑测试

```bash
python test_datalineage.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/namsafsalo/datalineage>

---

## 关于作者

namsafsalo 做数据版本谱系相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://namsafsalo.github.io>
- 仓库：<https://github.com/namsafsalo/datalineage>

## 许可

MIT，见 [LICENSE](LICENSE)。
