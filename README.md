# Xie-s-repo

Xie-s-repo/

\# 🏎️ STM32 \& Python 嵌入式反應時間測試系統 (Reaction Time Tester)



本專題為一套結合嵌入式微控制器 \*\*STM32 (NUCLEO-G474RE)\*\* 與上位機 \*\*Python (Jupyter Notebook)\*\* 的高精確度反應時間測試與紀錄系統。透過硬體狀態機（State Machine）控制三色 LED 與按鈕中斷（EXTI），配合微秒級定時器（TIM2）進行時間量測，並將數據傳送至 Python 端進行即時解析與成績顯示

├── .gitignore                     # Git 版本控制忽略檔 (自動過濾編譯中間檔與快取)

├── README.md                      # 專案說明文件

├── python terminal/               # Python 上位機程式資料夾

│   └── Untitled3(1).ipynb         # Jupyter Notebook 上位機監聽與數據解析腳本

└── stm32\_firmware/                # STM32 韌體專案資料夾 (STM32CubeIDE)

&#x20;   ├── Core/                      # 核心 C 語言程式碼與標頭檔

&#x20;   │   ├── Inc/                   # 標頭檔 (.h)

&#x20;   │   └── Src/                   # 源碼檔案 (main.c)

&#x20;   ├── Drivers/                   # STM32 HAL 庫與 CMSIS 驅動

&#x20;   └── stm32g474re.ioc            # STM32CubeMX 硬體腳位與週邊配置文件

