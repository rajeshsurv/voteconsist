# voteconsist

**用多模型投票评估答案可靠性。**

`voteconsist` —— 统计各模型答案的一致程度与分歧点，给出置信度

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`voteconsist.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install rajeshsurv-voteconsist
```

装完直接用命令名调用：

```bash
voteconsist --help
```

也可以不用安装，直接把 `voteconsist.py` 拷走用——它只依赖标准库。

## 为什么需要它

一致度高不等于对，但分歧是可靠的告警信号

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 多模型一致性投票 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python voteconsist.py --file input.txt
python voteconsist.py --text "示例内容"
python voteconsist.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_voteconsist.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/rajeshsurv/voteconsist>

---

## 关于作者

rajeshsurv 做多模型一致性投票相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://rajeshsurv.github.io>
- 仓库：<https://github.com/rajeshsurv/voteconsist>

## 许可

MIT，见 [LICENSE](LICENSE)。
