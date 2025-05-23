## 第五章：Monad 101 简短回答

### 1. 延迟执行
Monad 的延迟执行将交易共识与执行分离，先确定交易顺序，再执行交易。这种机制优化了共识与执行的关系，允许系统在共识后并行执行交易，提高了整体效率。

### 2. 乐观并行执行
乐观并行执行假设大多数交易不会冲突，允许同时处理多个交易。关键步骤包括：交易排序、依赖分析、并行执行、冲突检测和结果验证。

### 3. 并行执行与线性排序
Monad 通过先确定交易顺序（线性排序），然后分析交易依赖关系，确保并行执行时仍保持状态一致性。系统识别无冲突的交易进行并行处理，对有依赖的交易保持正确顺序。

### 4. monadBFT 特点
monadBFT 具有高吞吐量、低延迟和确定性最终性。相比传统 BFT，它简化了共识流程，降低了通信复杂性，并优化了验证者参与机制。

### 5. Optimistic Concurrency Control
Monad 采用 OCC 以提高并发性能。它允许交易并行执行，在提交前验证冲突，冲突时回滚重执行，减少了锁机制带来的性能损失。