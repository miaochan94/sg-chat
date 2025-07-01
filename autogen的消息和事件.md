# autogen的消息和事件

2025年6月4日 16:50

在 AutoGen 框架中，消息（Message）和事件（Event）是智能体之间通信的核心组成部分。根据官方文档 ，这些消息和事件类型被设计为继承自 BaseChatMessage 或BaseAgentEvent，用于在智能体之间传递信息或表示智能体的内部状态和行为。以下是对主要消息和事件类型的总结：

# 消息类型 （Messages）

消息类型用于智能体之间的通信，通常表示完整的交流内容。

1. TextMessage

• 描述：表示纯文本消息。• 用途：用于用户输入或智能体的文本回复。(pypi.org)

2. MultiModalMessage• 描述：支持多种内容类型的消息，如文本和图像。• 用途：用于需要传递图像、音频等多媒体内容的场景。

3. StructuredMessage• 描述：结构化的消息，内容为 Pydantic 模型。• 用途：用于需要结构化数据交换的场景。(microsoft.github.io)

4. StopMessage• 描述：表示会话的终止。用途：用于指示对话结束。 (microsoft.github.io)

5. ToolCallSummaryMessage• 描述：总结工具调用的消息。• 用途：用于提供工具调用的摘要信息。

6. HandoffMessage• 描述：用于智能体之间的任务交接。• 用途：在多智能体协作中，用于任务的转移。

# 事件类型 （      ）

事件类型用于表示智能体的内部状态、行为或与外部环境的交互，通常不用于智能体之间的直接通信。

1. ToolCallRequestEvent

• 描述：表示智能体请求调用某个工具。  
• 用途：用于触发外部工具或函数的调用。

2. ToolCallExecutionEvent• 描述：表示工具调用的执行结果。• 用途：用于传递工具调用后的返回值。(pypi.org)

3. MemoryQueryEvent

• 描述：表示对记忆模块的查询。  
• 用途：用于访问或检索智能体的记忆信息。

4. UserInputRequestedEvent• 描述：表示智能体请求用户输入。• 用途：用于需要用户提供额外信息的场景。

5. ModelClientStreamingChunkEvent• 描述：表示模型流式输出的一个片段。• 用途：用于处理模型的流式响应。

6. ThoughtEvent• 描述：表示智能体的思考过程。• 用途：用于展示智能体的推理或决策过程。

7. SelectSpeakerEvent• 描述：表示选择下一个发言的智能体。• 用途：用于多智能体对话中控制发言顺序。

8. CodeGenerationEvent• 描述：表示代码的生成过程。• 用途：用于展示智能体生成代码的行为。(newsletter.victordibia.com)

9. CodeExecutionEvent• 描述：表示代码的执行过程。• 用途：用于展示智能体执行代码的行为。

这些消息和事件类型的设计使得 AutoGen 能够灵活地处理多种交互模式，包括文本交流、多媒体内容、工具调用、记忆访问等，支持构建复杂的多智能体系统。  
如需深入了解每种类型的字段和方法，建议查阅官方文档：