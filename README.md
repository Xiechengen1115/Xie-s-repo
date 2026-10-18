# Xie-s-repo

Xie-s-repo/

# 🏎️ STM32 & Python 嵌入式反應時間測試系統 (Reaction Time Tester)

本專題為一套結合嵌入式微控制器 **STM32 (NUCLEO-G474RE)** 與上位機 **Python (Jupyter Notebook)** 的高精確度反應時間測試與紀錄系統。透過硬體狀態機（State Machine）控制三色 LED 與按鈕中斷（EXTI），配合微秒級定時器（TIM2）進行時間量測，並將數據傳送至 Python 端進行即時解析與成績顯示。

---

## 📁 專案目錄結構

```text
Xie-s-repo/
├── .gitignore                             # Git 版本控制忽略檔 (自動過濾編譯中間檔與快取)
├── README.md                              # 專案說明文件
├── python terminal/                       # Python 上位機程式資料夾
│   └── Untitled3(1).ipynb                 # Jupyter Notebook 上位機監聽、數據解析與單位轉換腳本
└── stm32_firmware/                        # STM32 韌體專案資料夾 (STM32CubeIDE)
    ├── Core/                              # 使用者核心程式碼與設定
    │   ├── Inc/                           # 標頭檔 (.h) 目錄
    │   │   ├── main.h                     # 全域腳位定義、狀態定義與主要標頭檔
    │   │   ├── stm32g4xx_hal_conf.h       # HAL 庫模組啟用與硬體參數設定檔
    │   │   └── stm32g4xx_it.h             # 中斷服務常式標頭檔
    │   └── Src/                           # 主程式與系統原始碼 (.c) 目錄
    │       ├── main.c                     # 主程式 (FSM狀態機、EXTI按鈕中斷、TIM2計時與UART發送)
    │       ├── stm32g4xx_hal_msp.c        # 微控制器支援套件 (MSP) 初始化程式
    │       ├── stm32g4xx_it.c             # 中斷處理函式 (Interrupt Service Routines)
    │       └── system_stm32g4xx.c         # 系統時鐘與核心底層初始化
    ├── Drivers/                           # 晶片原廠與 CMSIS 驅動庫
    │   ├── CMSIS/                         # ARM Cortex-M 核心標準介面與暫存器定義
    │   └── STM32G4xx_HAL_Driver/          # ST 官方 HAL 硬體抽象層驅動 (GPIO, TIM, UART等)
    ├── Startup/                           # 晶片啟動程式碼
    │   └── startup_stm32g474retx.s        # 組合語言啟動檔 (設定中斷向量表與堆疊)
    ├── .cproject                          # Eclipse / STM32CubeIDE 專案編譯設定檔
    ├── .project                           # Eclipse / STM32CubeIDE 專案架構檔
    ├── stm32g474re.ioc                    # STM32CubeMX 圖形化周邊配置專案檔
    └── STM32G474RETX_FLASH.ld             # 記憶體配置與鏈結腳本 (Linker Script)
