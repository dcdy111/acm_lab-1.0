---
author: 左岚
---

# UML和Mermaid语法详解

## UML语法（PlantUML）

### 1. 类图语法

```plantuml
@startuml
' 定义类
class 类名 {
    ' 属性
    -私有属性
    #protected属性
    ~package属性
    +公有属性
    
    ' 方法
    +公有方法()
    -私有方法()
}

' 抽象类
abstract 抽象类名 {
    {abstract} 抽象方法()
}

' 接口
interface 接口名 {
    方法1()
    方法2()
}

' 关系表示
类A <|-- 类B    : 继承
类A <|.. 类B    : 实现
类A *-- 类B    : 组合
类A o-- 类B    : 聚合
类A --> 类B    : 关联
类A ..> 类B    : 依赖
@enduml
```

### 2. 序列图语法

```plantuml
@startuml
' 定义参与者
participant 参与者A
actor 参与者B
database 数据库

' 消息传递
参与者A -> 参与者B: 同步消息
参与者A ->> 参与者B: 异步消息
参与者A --> 参与者B: 返回消息
参与者A -x 参与者B: 丢失消息

' 激活和停用
activate 参与者A
deactivate 参与者A

' 注释
note left of 参与者A: 左侧注释
note right of 参与者B: 右侧注释
note over 参与者A, 参与者B: 跨越注释
@enduml
```

### 3. 用例图语法

```plantuml
@startuml
' 定义角色
actor 用户
actor 管理员

' 定义用例
usecase (用例1)
usecase (用例2) as UC2

' 关系
用户 --> (用例1)
用户 --> (用例2)
(用例1) .> (用例2): <<include>>
(用例1) <. (用例3): <<extend>>

' 系统边界
rectangle 系统 {
    usecase (用例4)
    usecase (用例5)
}
@enduml
```

## Mermaid语法

### 1. 流程图语法

```mermaid
graph TD
    %% 节点定义
    A[方框]
    B(圆角框)
    C{菱形}
    D((圆形))
    E>不对称形状]
    
    %% 连接线
    A --> B    %% 箭头
    B --- C    %% 直线
    C -.-> D   %% 虚线箭头
    C ==> E    %% 粗箭头
    
    %% 带文本的连接
    A -->|是| B
    A -->|否| C
    
    %% 子图
    subgraph 子图标题
        子图内容
    end
```

### 2. 序列图语法

```mermaid
sequenceDiagram
    %% 参与者定义
    participant A as 参与者A
    participant B as 参与者B
    
    %% 消息传递
    A->>B: 实线箭头
    A-->>B: 虚线箭头
    A-xB: 带X箭头
    
    %% 激活框
    activate A
    A->>B: 消息
    deactivate A
    
    %% 注释
    Note left of A: 左侧注释
    Note right of B: 右侧注释
    Note over A,B: 跨越注释
```

### 3. 甘特图语法

```mermaid
gantt
    %% 图表属性
    title 项目计划
    dateFormat YYYY-MM-DD
    axisFormat %m/%d
    
    %% 定义部分
    section 项目阶段1
    任务1 :a1, 2024-01-01, 30d
    任务2 :after a1, 20d
    
    %% 里程碑
    section 里程碑
    里程碑 :milestone, 2024-02-01, 0d
```

### 4. ER图语法

```mermaid
erDiagram
    %% 实体定义
    CUSTOMER {
        string id
        string name
        string email
    }
    
    %% 关系定义
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ ORDER_ITEM : contains
    
    %% 关系类型
    %% ||--|| : 一对一
    %% }|--|{ : 多对多
    %% ||--o{ : 一对多
    %% }o--|| : 多对一
```

### 5. 状态图语法

```mermaid
stateDiagram-v2
    %% 状态定义
    [*] --> 初始状态
    初始状态 --> 状态1
    状态1 --> 状态2
    状态2 --> [*]
    
    %% 复合状态
    state 复合状态 {
        [*] --> 子状态1
        子状态1 --> 子状态2
    }
    
    %% 注释
    note right of 状态1: 状态说明
```

## 常用技巧

### 1. 样式设置

- PlantUML
```plantuml
@startuml
skinparam classAttributeIconSize 0
skinparam backgroundColor #EEEBDC
skinparam handwritten true

' 更多样式设置...
@enduml
```

- Mermaid
```mermaid
%%{init: {'theme': 'base', 'themeVariables': { 'primaryColor': '#ff0000'}}}%%
graph TD
    A[红色主题]
```

### 2. 布局控制

- PlantUML
```plantuml
@startuml
left to right direction
' 或
top to bottom direction
@enduml
```

- Mermaid
```mermaid
graph LR  % 左右布局
% 或
graph TD  % 上下布局
```

## 最佳实践

1. **命名规范**
   - 使用清晰、有意义的标识符
   - 保持命名风格一致
   - 避免特殊字符

2. **布局建议**
   - 保持图表简洁
   - 合理使用空间
   - 避免交叉线过多

3. **注释使用**
   - 适当添加注释说明
   - 使用注释解释复杂逻辑
   - 保持注释简洁明了 