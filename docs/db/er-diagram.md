# DB設計

## テーブル一覧

- `monthly_balances`: 月毎の収支
- `entries`: 収支項目
- `categories`: カテゴリ

## ER図

```mermaid
erDiagram
    monthly_balances {
        INT id PK
        DATETIME month_year "年月 (例: 2025-01)"
        INT balance "収支"
    }

    entries {
        INT id PK
        VARCHAR(128) name "名称"
        INT price "金額"
        INT category_id FK "カテゴリid"
        DATETIME entry_date "日付 (例: 2025-01-01)"
    }

    categories {
        INT id PK
        VARCHAR(32) name "カテゴリ名"
    }
