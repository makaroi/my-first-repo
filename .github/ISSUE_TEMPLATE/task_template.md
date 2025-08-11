name: タスク
description: 新しいタスクを登録します
title: "[Task] "
labels: [task]
assignees: []

body:
  - type: input
    id: project
    attributes:
      label: Project（タスクID）
      description: 任意のタスクID（例: UPJ-300）。未使用なら空でOK。
      placeholder: "UPJ-300"
    validations:
      required: false

  - type: dropdown
    id: plan_quarter
    attributes:
      label: Plan/Quarter
      description: 実施を想定している四半期
      options:
        - 2025Q3
        - 2025Q4
        - 2026Q1
        - 2026Q2
        - 2026Q3
        - 2026Q4
    validations:
      required: false

  - type: dropdown
    id: ltp
    attributes:
      label: Long-Term-Project
      description: 長期カテゴリ（Single select）
      options:
        - 雑巾（銀行・掃除など）
        - 人生進捗（美容院・友人と遊ぶなど）
        - 技術書を読む
        - 技術力をつける
    validations:
      required: false

  - type: input
    id: due
    attributes:
      label: Due date（締切 / 実施予定日）
      description: 例) 2025-08-31
      placeholder: "YYYY-MM-DD"
    validations:
      required: false

  - type: input
    id: estimate
    attributes:
      label: Estimate（見積：30分=1）
      description: 30分単位で数値入力（例: 2=1時間）
      placeholder: "2"
    validations:
      required: false

  - type: textarea
    id: description
    attributes:
      label: Description（背景・受け入れ条件）
      description: なぜやるか／終わりの定義（受け入れ条件）を記入
      placeholder: |
        背景:
        目的:
        完了条件（受け入れ条件）:
    validations:
      required: true

  - type: textarea
    id: ref
    attributes:
      label: Ref（参考リンク）
      description: 関連URLや資料
      placeholder: |
        - https://example.com
        - 関連Issue: #123
    validations:
      required: false

  - type: textarea
    id: todo
    attributes:
      label: Todo（チェックリスト）
      description: 実行手順をチェックボックスで
      placeholder: |
        - [ ] 手順1
        - [ ] 手順2
    validations:
      required: false

  - type: markdown
    attributes:
      value: |
        **メモ**  
        作成後、Projects側では自動で「Inbox」に入るようWorkflowsを設定済みです（`is:issue is:open`）。
