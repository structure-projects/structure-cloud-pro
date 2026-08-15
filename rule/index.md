# Structure-Projects 规范索引

## 方案切换说明

本目录包含三种提示词方案，支持智能切换：

| 方案 | 文件 | 用途 | 适用场景 |
|------|------|------|----------|
| **A+C混合** | 模块化文件 (01-06) | 精简版，核心规则提取 | 常规任务、快速开发 |
| **B备用** | `structure-projects-rule.md` | 完整原始内容 | A/C方案效果不佳时自动升级 |

## 自动切换机制

### 触发条件

当以下情况发生时，智能体应自动切换到B方案：

1. **任务复杂度高**：涉及多个组件的深度集成
2. **细节缺失**：精简版无法提供足够指导
3. **明确引用**：任务提到"参考完整规范"、"详细配置"等

### 切换命令

```
方案切换 → 加载 B方案: structure-projects-rule.md
```

## 模块化文件清单

| 模块 | 文件 | 核心内容 | 关联原始章节 |
|------|------|----------|--------------|
| 项目结构 | [01-project-structure.md](01-project-structure.md) | 四层架构、模块职责 | 第二章 |
| 依赖配置 | [02-dependency-config.md](02-dependency-config.md) | Maven配置、组件依赖 | 第三章 |
| CRUD模板 | [03-crud-template.md](03-crud-template.md) | 控制器/服务/管理器模板 | 第四章 |
| 组件集成 | [04-component-integration.md](04-component-integration.md) | 安全/Redis/MQ等集成 | 第七章 |
| 参数验证 | [05-validation.md](05-validation.md) | 验证注解、校验规则 | 第八章 |
| Swagger规范 | [06-swagger.md](06-swagger.md) | 文档生成、注解使用 | 第九章 |

## 快速参考

### 命名规范速查

```
{业务}StateEnum      → 状态枚举
{业务}TypeEnum       → 类型枚举
{业务}ExceptionEnum  → 错误码枚举
I{业务}Service       → Service接口
{业务}ServiceImpl    → Service实现
{业务}Controller    → 控制器
{业务}Mapper        → Mapper接口
{业务}Assembler     → 装配器
```

### 响应规范

```java
ResultUtilSimpleImpl.success(data);
ResultUtilSimpleImpl.fail(code, message);
```

### 异常规范

```java
throw new CommonException(枚举.getCode(), 枚举.getMessage());
```

## 使用指南

### 1. 优先使用精简模块

对于标准CRUD、简单组件集成等任务，优先加载对应模块文件。

### 2. 组合使用

复杂任务可组合多个模块：

```
加载: 01-project-structure.md + 03-crud-template.md + 05-validation.md
```

### 3. 升级到完整版

当需要深入理解某个组件的配置细节或完整代码示例时：

```
切换到: structure-projects-rule.md
参考章节: [对应模块名称]
```

## 关联映射

每个模块文件末尾都包含 `## 完整版关联` 章节，指向原始文件中对应的详细章节，便于快速定位。

---

**文件位置**: `/rule/`
**原始完整版**: `structure-projects-rule.md` (B方案)
