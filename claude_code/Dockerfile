# 使用輕量級的 Node.js 20 環境
FROM node:20-bookworm-slim

# 安裝基礎開發工具與常用維運/網路工具 (Git, SSH, Curl, Python3 等)
RUN apt-get update && apt-get install -y \
    git \
    curl \
    wget \
    jq \
    tree \
    openssh-client \
    python3 \
    unzip \
    && rm -rf /var/lib/apt/lists/*

# 安裝 Bun
RUN curl -fsSL https://bun.sh/install | bash

# 設定 Bun 環境變數
ENV PATH="$BUN_INSTALL/bin:$PATH"

# 全域安裝 Claude Code CLI
RUN npm install -g @anthropic-ai/claude-code

# 設定預設工作目錄
WORKDIR /workspace

# 預設執行 bash，讓我們可以互動式操作
CMD ["bash"]
