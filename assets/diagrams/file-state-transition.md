---
title: "図: ファイルの状態遷移"
purpose: "Untracked → Staged → Committed → Pushed の流れを示す"
used_in:
  - "01-concepts.md"
---

# ファイルの状態遷移

```mermaid
stateDiagram-v2
    [*] --> Untracked: ファイル作成
    Untracked --> Staged: + ボタン (ステージング)
    Staged --> Committed: Commit
    Committed --> Pushed: Push
    Pushed --> [*]
    Staged --> Untracked: - ボタン (ステージング解除)
    Committed --> Staged: 修正→再ステージング
```

| 状態 | VSCodeでの見え方 |
|------|------------------|
| Untracked（追跡外） | Source Control の「Changes」に表示 |
| Staged（ステージ済） | 「Staged Changes」に表示 |
| Committed（セーブ済） | Graph に履歴として表示（ローカルのみ） |
| Pushed（共有済） | Graph に `origin/` 付きで表示 |
