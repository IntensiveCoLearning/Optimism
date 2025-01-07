---
timezone: Asia/Shanghai
---

---

# {Zedz}

1. 自我介绍
zedz，8月份参与过两次共学，区块链爱好者，重新回来学习。

2. 你认为你会完成本次残酷学习吗？
会

## Notes

<!-- Content_START -->

### 2025.01.06

Optimistic Rollup 概述
Optimism 是一种叫做 “Optimistic Rollup” 的技术。它的核心思想就是，Optimism 这个区块链依赖于另外一个已经存在的区块链（比如以太坊）的安全性和共识机制。简单来说，Optimism 就是把以太坊当作“妈妈区块链”，而它自己是“孩子区块链”。

1. 区块存储
Optimism 把数据存储到以太坊的区块链上，但是采用了特别的方式，这样做可以省钱。数据一旦提交，就无法再修改或删减，这样保证了数据的安全性和完整性。

2. 区块生产
在 Optimism 上，区块的生产是由一个叫做 “sequencer” 的角色来负责。它的工作包括：

确认交易并更新区块链的状态。
创建和执行 Optimism 上的区块。
将交易提交到以太坊区块链上。
这些区块每两秒钟就会生成一次，不管它们是否有交易，或者是空的。

3. 交易提交
交易有两种方式进入 Optimism：

直接提交：这种交易便宜，因为不需要通过以太坊。但是，这些交易不能保证完全公平，因为只有 sequencer 知道它们。
通过以太坊提交：这种方式可以确保交易公平，避免 sequencer 偷偷删减交易。
4. 区块执行
区块的执行由一个叫做 “执行引擎” 来完成。它通过和其他引擎交换信息来更新状态，也可以通过区块链本身来获取信息。虽然后者比较慢，但它能够保证数据的安全性。

5. ETH 和代币的跨链转账
Optimism 允许在不同区块链之间转账，比如从以太坊转到 Optimism，或者从 Optimism 转回以太坊。这个转账过程通过“桥接”来完成。你可以把代币从以太坊转到 Optimism，也可以把它们从 Optimism 取回。

6. 从以太坊到 Optimism
在 Optimism 里面，从以太坊转到 Optimism 的交易叫做 “存款”。这些存款会进入一个特定的区块，几分钟后，Optimism 就会确认这个存款。

7. 从 Optimism 到以太坊
从 Optimism 转到以太坊的操作叫做 “提取”，需要分为三个步骤：

首先发起提取请求。
等待一个新的根状态提交到以太坊。
最后，确认提取请求。
8. 故障证明
在 Optimism 中，数据提交到以太坊后不会立即验证它的正确性，而是会在一定时间内等待挑战。如果没人提出挑战，数据就被认为是正确的；如果有人挑战成功，数据就会被撤回。

### 2024.01.07

1. Layer 2扩容技术概述
随着以太坊的使用量激增，去中心化金融（DeFi）和NFT市场的发展都对以太坊的吞吐量提出了更高的要求。然而，以太坊每秒只能处理不到20笔交易，且高昂的gas费用限制了更多用户的参与。因此，Layer 2 解决方案应运而生，它们能够在以太坊主链（Layer 1）上执行一些计算和存储操作，从而降低费用和提高效率。

Layer 2的扩容方案：

Optimistic Rollup
ZK Rollup
Plasma
Validium
2. 各解决方案的交易费用
文章中的一个核心点是 Gas 费用。下面总结了不同扩容技术方案的费用差异：

ZK Rollup：在 zkSync 上，每笔交易的成本有两个组成部分：链下部分（存储 + SNARK 生成成本）和链上部分（验证成本）。总体来看，ZK Rollup 的交易成本较低，且随着以太坊网络更新，EIP-4488等提案将进一步降低交易费用。

Optimistic Rollup：采用“乐观假设”，所有交易假设是合法的，只有在挑战的情况下才进行验证。Optimism的费用相较于ZK Rollup较高，但其安全性和兼容性方面表现出色。Optimism 在交易中有两个主要成本来源：

L2执行费：这是交易在Layer 2上的执行费用。
L1数据/安全费用：Optimism的所有交易都需提交到以太坊主链，这会引入额外的费用。
zkPorter：zkSync 2.0 提出的 zkPorter 技术通过降低数据可用性成本来大幅降低交易费用。由于zkPorter不依赖于链上数据可用性，它的交易费用预计会比ZK Rollup便宜得多（约为0.03美元）。

3. 交易费用的影响因素
EIP-4488：该提案将大幅降低 Layer 2 Rollup 的成本，特别是对 calldata（数据传输）带来了显著的影响。预计将大幅降低 non-zero calldata 的gas费用。

ZK Rollup和Optimistic Rollup的区别：ZK Rollup通常提供更低的费用和更高的吞吐量，尤其在转账ETH和ERC20代币时。Optimistic Rollup则更侧重于兼容性和安全性，但相较之下，费用较高。

4. ZK Rollup的优势
高扩展性：ZK Rollup在理论上能够提供比Ethereum主网高100倍以上的TPS。例如，ZK Rollup最大可以实现每秒11,818笔交易，远高于Ethereum的101笔TPS。
低成本：由于压缩了数据量，ZK Rollup的费用显著低于传统Ethereum交易。
安全性：ZK Rollup能够通过零知识证明（SNARK）确保安全性，并且其数据验证不依赖于Layer 2的信任模型，而是依赖于Ethereum主链的安全性。
5. 未来发展
随着 Layer 2 方案的不断发展，我们可能会看到更多的应用迁移到 Layer 2 上，以获得更好的用户体验。例如，Uniswap等去中心化交易所（DEX）可能会在ZK Rollup和zkPorter上部署智能合约，提供更低成本的交易。

总结
ZK Rollup 是目前最具扩展性和最低成本的解决方案，尤其适合需要高吞吐量的应用（如DeFi和NFT）。
Optimistic Rollup 提供了更强的兼容性和安全性，适用于更广泛的用例，但其费用相对较高。
zkPorter 预计会成为一种重要的低费用方案，尤其在不需要链上数据可用性的情况下，交易费用可以进一步降低。
随着技术进步和以太坊扩展性提案（如EIP-4488和EIP-4844）的实施，未来Layer 2的费用将大幅降低，从而推动以太坊生态的广泛应用。

---

Rollups的三阶段发展框架
Rollups是以太坊扩展的一种技术，但它们需要逐步去中心化，才能完全做到安全和可靠。为了更好地理解rollups的成熟度，我们将它们分为三个阶段：

第一阶段：完全“辅助轮”
控制权在运营者手中：在这个阶段，rollup完全由运营者控制。
数据根状态在L1上发布：rollup的状态信息会被发布到以太坊主链（L1），方便后期验证和恢复。
透明性高：有软件可以用来重建rollup的状态，任何人都可以审查这个过程，增加系统的可信度。
第二阶段：有限的“辅助轮”
由智能合约治理：rollup开始由智能合约来治理，但可能会保留一个“安全委员会”，用来修复一些问题。
存在欺诈证明系统：如果有不正确的状态根，系统会用欺诈证明来处理。
允许外部验证：至少有5个外部参与者可以提交欺诈证明，保证系统的透明性。
用户可以自己退出：用户在不想继续使用时，可以自己把资产取出，不依赖运营者。
有安全委员会：这个委员会至少有8个成员，通过集体投票来决定系统的重要问题。
第三阶段：完全去中心化
完全去中心化的欺诈证明系统：任何人都可以提交欺诈证明，不再有任何限制。
用户可以有更长时间退出：如果不喜欢系统的升级或变化，用户至少可以有30天的时间退出。
安全委员会的作用有限：安全委员会只能处理系统中出现的严重错误，不能随便干预系统的其他部分。
总结
这个框架帮助我们理解rollups的成长过程。从完全由运营者控制到完全去中心化，它的逐步发展确保了系统的安全和去信任化。这有助于我们评估rollups是否已经准备好成为一个完全安全、无需信任的以太坊扩展解决方案。

### 2024.01.08

todo - 看群里的优秀笔记

### 2024.01.09

### 2024.01.10

### 2024.01.11

### 2024.01.12

### 2024.01.13

### 2024.01.14

### 2024.01.15

### 2024.01.16

### 2024.01.17

### 2024.01.18

### 2024.01.19

### 2024.01.20

### 2024.01.21

### 2024.01.22

### 2024.01.23

### 2024.01.24

### 2024.01.25

### 2024.01.26


<!-- Content_END -->