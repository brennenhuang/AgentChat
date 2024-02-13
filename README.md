

# 執行
```
poetry add fastapi
poetry add "uvicorn[standard]"
poetry add "pydantic[email]"
```
```
uvicorn app.main:app --reload

```

# 複習docker
```
docker build -t test_backend:1.0.2 .
```

```
docker run test_backend:1.0.2
```

開port出來
```
docker run -p 8080: 8080 test_backend:1.0.2
```

# 資料架構圖
```
ecommerce-platform/
│
├── app/                      # 應用程式主資料夾
│   ├── api/                  # API路由和視圖
│   │   ├── endpoints/        # 分模塊的端點 (例如，users.py, items.py)
│   │   └── dependencies/     # 依賴性注入 (例如，資料庫會話, 認證)
│   │
│   ├── core/                 # 應用程式配置和核心設定
│   │   ├── config.py         # 配置設定 (例如，資料庫URL, 密鑰)
│   │   └── security.py       # 安全性和認證功能
│   │
│   ├── crud/                 # CRUD操作 (建立、讀取、更新、刪除)
│   │   ├── crud_user.py      # 用戶模型的CRUD操作
│   │   ├── crud_item.py      # 商品模型的CRUD操作
│   │   └── crud_order.py     # 訂單模型的CRUD操作
│   │
│   ├── db/                   # 資料庫相關的模塊
│   │   ├── base_class.py     # Base類別定義
│   │   ├── init_db.py        # 資料庫初始化和種子資料
│   │   └── session.py        # 資料庫會話管理
│   │
│   ├── models/               # 資料模型定義
│   │   ├── user.py           # 用戶模型
│   │   ├── item.py           # 商品模型
│   │   └── order.py          # 訂單模型
│   │
│   ├── schemas/              # Pydantic模型（用於請求和響應的資料驗證）
│   │   ├── user.py           # 用戶模式
│   │   ├── item.py           # 商品模式
│   │   └── order.py          # 訂單模式
│   │
│   └── main.py               # FastAPI應用實例和路由註冊
│
├── tests/                    # 測試模塊
│   ├── test_api/             # API端點的測試
│   └── test_db/              # 資料庫操作的測試
│
├── alembic/                  # 資料庫遷移
│   └── versions/             # 遷移腳本
│
├── requirements.txt          # 專案依賴
└── README.md                 # 專案說明文件
```