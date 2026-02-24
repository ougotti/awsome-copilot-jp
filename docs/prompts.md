# Prompts 一覧と活用ガイド

> [github/awesome-copilot](https://github.com/github/awesome-copilot) で公開されている **138 個の Prompts** を日本語で解説します。

## Prompts とは

Prompts は、Copilot Chat の `/` コマンドから呼び出せる**再利用可能なタスクテンプレート**です。繰り返し行う定型作業をテンプレート化することで、一貫した品質の出力を得られます。

Instructions が「自動適用されるルール」、Agents が「相談相手の専門家」なら、Prompts は「定型タスクのレシピ」です。

### 設定方法

```
.github/
  prompts/
    create-readme.prompt.md
    generate-jest-tests.prompt.md
```

Copilot Chat で `/create-readme` のように入力すると呼び出せます。

---

## カテゴリ別 Prompts 一覧

### ドキュメント生成

#### README・仕様書

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-readme.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-readme.prompt.md) | README.md 作成 | プロジェクトルートの README.md |
| [`create-specification.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-specification.prompt.md) | AI 向け仕様書作成 | `/spec/spec-*.md` |
| [`create-architectural-decision-record.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-architectural-decision-record.prompt.md) | ADR（アーキテクチャ決定記録）作成 | `/docs/adr/adr-NNNN-*.md` |
| [`create-technical-spike.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-technical-spike.prompt.md) | 技術スパイクドキュメント作成 | `/spikes/*-spike.md` |
| [`documentation-writer.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/documentation-writer.prompt.md) | Diataxis フレームワークに基づくドキュメント | チュートリアル、How-to、リファレンス、説明 |
| [`create-tldr-page.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-tldr-page.prompt.md) | TLDR ページ作成 | コマンドの簡潔な説明 |
| [`tldr-prompt.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/tldr-prompt.prompt.md) | TLDR 形式の説明 | 簡潔な概要 |
| [`readme-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/readme-blueprint-generator.prompt.md) | README 設計図生成 | README の構造案 |

**[create-readme.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/create-readme.prompt.md) の特徴:
- ワークスペース全体をレビューして README を生成
- GitHub Flavored Markdown（GFM）+ admonition 構文
- 過剰な絵文字を避けた簡潔なコンテンツ
- LICENSE/CONTRIBUTING/CHANGELOG は別ファイルに（README には含めない）

**[create-specification.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/create-specification.prompt.md) の特徴:
- AI 向けに最適化された機械可読な仕様書
- 明確で曖昧さのない言語
- `/spec/` ディレクトリに保存
- 11 セクション構成（Introduction, Requirements, Acceptance Criteria 等）
- YAML フロントマター（title, version, dates, owner, tags）

**[create-architectural-decision-record.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/create-architectural-decision-record.prompt.md) の特徴:
- `/docs/adr/` に連番で保存（adr-0001-*, adr-0002-* ...）
- ステータス追跡（Proposed/Accepted/Rejected/Superseded/Deprecated）
- Consequences セクション（POS/NEG コーディング）
- 代替案と却下理由の文書化

---

#### 計画・設計

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-implementation-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-implementation-plan.prompt.md) | 実装計画作成 | `/plan/[purpose]-[component]-[version].md` |
| [`update-implementation-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-implementation-plan.prompt.md) | 実装計画更新 | 既存計画の更新 |
| [`breakdown-epic-pm.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-epic-pm.prompt.md) | Epic PRD 作成（PM 向け） | `/docs/ways-of-work/plan/{epic}/epic.md` |
| [`breakdown-epic-arch.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-epic-arch.prompt.md) | Epic アーキテクチャ仕様（アーキテクト向け） | `/docs/ways-of-work/plan/{epic}/arch.md` |
| [`breakdown-feature-prd.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-feature-prd.prompt.md) | Feature PRD 作成 | `/docs/ways-of-work/plan/{epic}/{feature}/prd.md` |
| [`breakdown-feature-implementation.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-feature-implementation.prompt.md) | Feature 実装計画 | `/docs/ways-of-work/plan/{epic}/{feature}/implementation-plan.md` |
| [`breakdown-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-plan.prompt.md) | GitHub プロジェクト計画 | project-plan.md + issues-checklist.md |
| [`breakdown-test.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-test.prompt.md) | テスト戦略・QA 計画 | テスト戦略、Issue チェックリスト、QA 計画 |
| [`architecture-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/architecture-blueprint-generator.prompt.md) | アーキテクチャ設計図生成 | アーキテクチャ図 |
| [`code-exemplars-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/code-exemplars-blueprint-generator.prompt.md) | コード例設計図生成 | コード例の構造 |
| [`copilot-instructions-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/copilot-instructions-blueprint-generator.prompt.md) | Copilot Instructions 設計図 | Instructions ファイル構造 |
| [`folder-structure-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/folder-structure-blueprint-generator.prompt.md) | フォルダ構造設計図 | ディレクトリ構造 |
| [`project-workflow-analysis-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/project-workflow-analysis-blueprint-generator.prompt.md) | プロジェクトワークフロー分析 | ワークフロー設計 |
| [`technology-stack-blueprint-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/technology-stack-blueprint-generator.prompt.md) | 技術スタック設計図 | 技術選定ガイド |

**[create-implementation-plan.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/create-implementation-plan.prompt.md) の特徴:
- AI-to-AI コミュニケーション向けの決定論的言語
- Purpose プレフィックス: `upgrade`, `refactor`, `feature`, `data`, `infrastructure`, `process`, `architecture`, `design`
- 8 セクション構成（Requirements, Implementation Steps, Alternatives, Dependencies, Files, Testing, Risks, Related Specs）
- 標準 ID プレフィックス（REQ-, TASK-, SEC-, CON-）
- 具体的なファイルパスと関数名を含む

**[breakdown-epic-pm.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-epic-pm.prompt.md) の特徴:
- SaaS プラットフォーム向け Epic PRD
- 8 セクション構成（Epic Name, Goal, User Personas, User Journeys, Business Requirements, Success Metrics, Out of Scope, Business Value）
- 機能要件と非機能要件の分離
- KPI の定義

**[breakdown-test.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/breakdown-test.prompt.md) の特徴:
- ISTQB / ISO 25010 準拠
- GitHub Issue テンプレート生成（テスト戦略: 2-3 SP、Playwright E2E: 2-5 SP、QA 検証: 3-5 SP）
- 品質目標: > 80% 行カバレッジ、> 90% ブランチカバレッジ（クリティカルパス）

---

### MCP サーバー生成

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`python-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/python-mcp-server-generator.prompt.md) | Python MCP サーバー生成 | 完全な Python プロジェクト |
| [`typescript-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/typescript-mcp-server-generator.prompt.md) | TypeScript MCP サーバー生成 | 完全な Node.js/TypeScript プロジェクト |
| [`csharp-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-mcp-server-generator.prompt.md) | C# MCP サーバー生成 | 完全な C# コンソールアプリ |
| [`go-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/go-mcp-server-generator.prompt.md) | Go MCP サーバー生成 | 完全な Go プロジェクト |
| [`java-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-mcp-server-generator.prompt.md) | Java MCP サーバー生成 | Maven/Gradle プロジェクト |
| [`rust-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/rust-mcp-server-generator.prompt.md) | Rust MCP サーバー生成 | 完全な Rust プロジェクト |
| [`kotlin-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/kotlin-mcp-server-generator.prompt.md) | Kotlin MCP サーバー生成 | Kotlin プロジェクト |
| [`ruby-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/ruby-mcp-server-generator.prompt.md) | Ruby MCP サーバー生成 | 完全な Ruby プロジェクト |
| [`php-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/php-mcp-server-generator.prompt.md) | PHP MCP サーバー生成 | 完全な PHP プロジェクト |
| [`swift-mcp-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/swift-mcp-server-generator.prompt.md) | Swift MCP サーバー生成 | Swift 6.0+ プロジェクト |
| [`mcp-copilot-studio-server-generator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/mcp-copilot-studio-server-generator.prompt.md) | Copilot Studio MCP サーバー | Copilot Studio 連携 |

**MCP サーバー生成プロンプトの共通特徴:**
- 完全なプロジェクト構造（設定ファイル、ディレクトリ構成）
- 公式 MCP SDK の使用
- ツール、リソース、プロンプトの実装例
- エラーハンドリングとロギング
- テストスイート
- Claude Desktop 統合手順

**[python-mcp-server-generator.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/python-mcp-server-generator.prompt.md) の特徴:
- `uv` パッケージマネージャー使用
- FastMCP サーバー実装
- デコレーター付きツール関数
- 型ヒント、docstring、async サポート
- PEP 8 準拠

**[typescript-mcp-server-generator.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/typescript-mcp-server-generator.prompt.md) の特徴:
- `@modelcontextprotocol/sdk` + `zod` 依存関係
- ES モジュールサポートの `tsconfig.json`
- McpServer クラス + zod バリデーションスキーマ
- MCP Inspector テスト手順

---

### テスト生成

#### JavaScript/TypeScript

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`javascript-typescript-jest.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/javascript-typescript-jest.prompt.md) | Jest テストガイド | Jest テスト規約 |

**[javascript-typescript-jest.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/javascript-typescript-jest.prompt.md) の特徴:
- テストファイル命名規則（`.test.ts`/`.test.js`）
- 分離テクニック（`jest.mock()`, `jest.spyOn()`）
- async テストパターン
- React Testing Library との組み合わせ
- Jest マッチャーリファレンス

---

#### C# テスト

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`csharp-xunit.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-xunit.prompt.md) | xUnit テストガイド | xUnit テスト規約 |
| [`csharp-nunit.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-nunit.prompt.md) | NUnit テストガイド | NUnit テスト規約 |
| [`csharp-mstest.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-mstest.prompt.md) | MSTest テストガイド | MSTest テスト規約 |
| [`csharp-tunit.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-tunit.prompt.md) | TUnit テストガイド | TUnit テスト規約（.NET 8.0+） |

**[csharp-xunit.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-xunit.prompt.md) の特徴:
- `[Fact]` と `[Theory]` 属性
- AAA（Arrange-Act-Assert）パターン
- データ駆動テスト（`[InlineData]`, `[MemberData]`, `[ClassData]`）

**[csharp-mstest.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-mstest.prompt.md) の特徴:
- MSTest 3.x/4.x の最新機能
- `[DataRow]` と `DynamicData`
- `[Retry]`, `[Timeout]` などの高度な機能
- ワークアイテムトレーサビリティ

**[csharp-tunit.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-tunit.prompt.md) の特徴:
- .NET 8.0+ 必須
- 非同期 Fluent アサーション（`await Assert.That(value).IsEqualTo(expected)`）
- デフォルトで並列実行
- `[Arguments]`, `[MethodData]`, `[ClassData]` によるデータ駆動

---

#### Java テスト

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`java-junit.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-junit.prompt.md) | JUnit 5 テストガイド | JUnit 5 テスト規約 |
| [`java-docs.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-docs.prompt.md) | Java ドキュメント生成 | Javadoc |

**[java-junit.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/java-junit.prompt.md) の特徴:
- JUnit 5 ライフサイクル管理（`@BeforeEach`, `@AfterEach`）
- Arrange-Act-Assert パターン
- パラメータ化テスト（`@ParameterizedTest`, `@ValueSource`, `@CsvSource`, `@MethodSource`）
- タグ付け、ネスト、順序付けによるテスト組織化

---

#### Playwright（E2E テスト）

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`playwright-generate-test.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/playwright-generate-test.prompt.md) | Playwright テスト生成 | TypeScript Playwright テスト |
| [`playwright-explore-website.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/playwright-explore-website.prompt.md) | Web サイト探索 | UI 要素ドキュメント、テストケース提案 |
| [`playwright-automation-fill-in-form.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/playwright-automation-fill-in-form.prompt.md) | フォーム自動入力 | フォーム操作自動化 |

**[playwright-generate-test.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/playwright-generate-test.prompt.md) の特徴:
- 「理解してからコード」の構造化手法
- `@playwright/test` 使用
- `tests/` ディレクトリに保存
- 反復的なテスト検証

**[playwright-explore-website.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/playwright-explore-website.prompt.md) の特徴:
- 3-5 のコア機能/ユーザーフローを特定
- UI 要素ロケーターとインタラクションパターンの文書化
- テストケース提案

---

#### Python テスト

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`pytest-coverage.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/pytest-coverage.prompt.md) | pytest カバレッジ分析 | 100% カバレッジ達成まで反復 |

**[pytest-coverage.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/pytest-coverage.prompt.md) の特徴:
- `cov_annotate` ディレクトリにカバレッジレポート生成
- 未カバー行（`!` マーク）の特定
- 反復的なテスト追加で 100% カバレッジ達成

---

### SQL・データベース

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`sql-optimization.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/sql-optimization.prompt.md) | SQL 最適化 | 最適化された SQL クエリ |
| [`sql-code-review.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/sql-code-review.prompt.md) | SQL コードレビュー | セキュリティ・パフォーマンスレビュー |
| [`postgresql-optimization.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/postgresql-optimization.prompt.md) | PostgreSQL 最適化 | PostgreSQL 固有の最適化 |
| [`postgresql-code-review.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/postgresql-code-review.prompt.md) | PostgreSQL コードレビュー | PostgreSQL 固有のレビュー |
| [`cosmosdb-datamodeling.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/cosmosdb-datamodeling.prompt.md) | Cosmos DB データモデリング | データモデル設計 |

**[sql-optimization.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/sql-optimization.prompt.md) の特徴:
- MySQL, PostgreSQL, SQL Server, Oracle 対応
- クエリチューニング、インデックス戦略
- アンチパターン特定（相関サブクエリ → ウィンドウ関数）
- DB 固有の最適化戦略

**[sql-code-review.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/sql-code-review.prompt.md) の特徴:
- 優先度レベルとリスク評価
- セキュリティ問題（SQL インジェクション、アクセス制御）
- Before/After コード例
- セキュリティ、パフォーマンス、保守性、スキーマ品質のスコア

**[postgresql-optimization.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/postgresql-optimization.prompt.md) の特徴:
- PostgreSQL 固有機能（JSONB, 配列, ウィンドウ関数, 全文検索）
- インデックス戦略（GIN, 複合, 部分, 式インデックス）
- 拡張機能推奨（uuid-ossp, pgcrypto）

**[cosmosdb-datamodeling.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/cosmosdb-datamodeling.prompt.md) の特徴:
- ペアプログラミング形式でインタラクティブに要件収集
- 集約指向設計原則
- パーティションキー戦略
- マルチエンティティドキュメントパターン（30-70% アクセス相関時）
- RU コスト計算

---

### コンテナ・Docker

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`multi-stage-dockerfile.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/multi-stage-dockerfile.prompt.md) | マルチステージ Dockerfile 生成 | 最適化された Dockerfile |
| [`containerize-aspnetcore.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/containerize-aspnetcore.prompt.md) | ASP.NET Core コンテナ化 | Linux Docker 環境向け Dockerfile |
| [`containerize-aspnet-framework.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/containerize-aspnet-framework.prompt.md) | ASP.NET Framework コンテナ化 | Windows Docker 環境向け Dockerfile |

**[multi-stage-dockerfile.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/multi-stage-dockerfile.prompt.md) の特徴:
- 言語/フレームワークを問わず適用可能
- ビルダーステージとランタイムステージの分離
- レイヤー最適化とキャッシュ活用
- セキュリティベストプラクティス（non-root ユーザー）
- ヘルスチェック設定

**[containerize-aspnetcore.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/containerize-aspnetcore.prompt.md) の特徴:
- .NET バージョン検出と SDK/ランタイムイメージ選択
- Linux ディストリビューション選択（Alpine, Ubuntu, Chiseled, Azure Linux）
- `.dockerignore` 生成
- non-root ユーザー実行設定

**[containerize-aspnet-framework.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/containerize-aspnet-framework.prompt.md) の特徴:
- Windows Server Core ベースイメージ
- IIS 設定、GAC アセンブリ、COM コンポーネント対応
- LogMonitor 設定
- ServiceMonitor 統合

---

### GitHub・CI/CD

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-github-action-workflow-specification.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-action-workflow-specification.prompt.md) | GitHub Actions ワークフロー仕様 | `/spec/spec-process-cicd-*.md` |
| [`create-github-issue-feature-from-specification.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-issue-feature-from-specification.prompt.md) | 仕様から GitHub Issue 作成 | 単一の GitHub Issue |
| [`create-github-issues-feature-from-implementation-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-issues-feature-from-implementation-plan.prompt.md) | 実装計画から GitHub Issues 作成 | フェーズごとの Issue |
| [`create-github-issues-for-unmet-specification-requirements.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-issues-for-unmet-specification-requirements.prompt.md) | 未達成要件の Issue 作成 | 要件ギャップの Issue |
| [`create-github-pull-request-from-specification.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-pull-request-from-specification.prompt.md) | 仕様から PR 作成 | GitHub Pull Request |
| [`conventional-commit.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/conventional-commit.prompt.md) | Conventional Commits 形式 | `type(scope): description` 形式のコミット |
| [`git-flow-branch-creator.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/git-flow-branch-creator.prompt.md) | Git Flow ブランチ作成 | feature/release/hotfix ブランチ |
| [`my-issues.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/my-issues.prompt.md) | 自分の Issue 一覧 | 担当 Issue リスト |
| [`my-pull-requests.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/my-pull-requests.prompt.md) | 自分の PR 一覧 | 担当 PR リスト |

**[create-github-action-workflow-specification.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/create-github-action-workflow-specification.prompt.md) の特徴:
- AI 最適化された CI/CD 仕様書
- Mermaid 実行フロー図
- Jobs/Dependencies マトリクス
- 要件マトリクス（機能、セキュリティ、パフォーマンス）
- 入出力契約とシークレット管理

**[conventional-commit.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/conventional-commit.prompt.md) の特徴:
- `git status` と `git diff` で変更を分析
- 標準フォーマット: `type(scope): description`
- タイプ: feat, fix, docs, style, refactor, perf, test, build, ci, chore, revert
- Breaking Changes とIssue 参照のフッター

---

### Azure

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`az-cost-optimize.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/az-cost-optimize.prompt.md) | Azure コスト最適化 | 最適化推奨 + GitHub Issues |
| [`azure-resource-health-diagnose.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/azure-resource-health-diagnose.prompt.md) | Azure リソースヘルス診断 | 7 ステップの診断レポート |
| [`update-avm-modules-in-bicep.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-avm-modules-in-bicep.prompt.md) | AVM モジュール更新 | 更新された Bicep ファイル |

**[az-cost-optimize.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/az-cost-optimize.prompt.md) の特徴:
- Azure IaC ファイル（Bicep, Terraform, ARM）を分析
- 個別の最適化ごとに GitHub Issue 作成
- マスター EPIC Issue（アーキテクチャ図、優先度順推奨）
- 優先度スコア: (Value Score × Monthly Savings) / (Risk Score × Implementation Days)

**[azure-resource-health-diagnose.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/azure-resource-health-diagnose.prompt.md) の特徴:
- 7 ステップのワークフロー
- Log Analytics / Application Insights（KQL クエリ）
- 重大度分類（critical, high, medium, low）
- 根本原因分析（設定、リソース制約、ネットワーク、アプリケーション、依存関係、セキュリティ）
- Azure CLI コマンド付きの段階的修復手順

---

### コードレビュー・リファクタリング

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`review-and-refactor.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/review-and-refactor.prompt.md) | コードレビュー＆リファクタリング | リファクタリング済みコード |
| [`ai-prompt-engineering-safety-review.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/ai-prompt-engineering-safety-review.prompt.md) | プロンプトエンジニアリング安全レビュー | 安全性評価 |

**[review-and-refactor.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/review-and-refactor.prompt.md) の特徴:
- `.github/instructions/*.md` のプロジェクトルールに従う
- `.github/copilot-instructions.md` も参照
- ファイル構造を維持（断片化なし）
- 既存テストをパス

---

### Spring Boot / Java

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-spring-boot-java-project.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-spring-boot-java-project.prompt.md) | Spring Boot（Java）プロジェクト作成 | Spring Boot プロジェクト |
| [`create-spring-boot-kotlin-project.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-spring-boot-kotlin-project.prompt.md) | Spring Boot（Kotlin）プロジェクト作成 | Spring Boot Kotlin プロジェクト |
| [`java-springboot.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-springboot.prompt.md) | Spring Boot ガイド | Spring Boot 規約 |
| [`kotlin-springboot.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/kotlin-springboot.prompt.md) | Kotlin Spring Boot ガイド | Kotlin Spring Boot 規約 |
| [`java-refactoring-extract-method.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-refactoring-extract-method.prompt.md) | Java メソッド抽出リファクタリング | リファクタリング済みコード |
| [`java-refactoring-remove-parameter.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-refactoring-remove-parameter.prompt.md) | Java パラメーター削除リファクタリング | リファクタリング済みコード |
| [`java-add-graalvm-native-image-support.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/java-add-graalvm-native-image-support.prompt.md) | GraalVM Native Image サポート追加 | Native Image 設定 |

---

### .NET

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`dotnet-upgrade.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dotnet-upgrade.prompt.md) | .NET アップグレード | アップグレードされたプロジェクト |
| [`dotnet-best-practices.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dotnet-best-practices.prompt.md) | .NET ベストプラクティス | 規約ガイド |
| [`dotnet-design-pattern-review.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dotnet-design-pattern-review.prompt.md) | .NET デザインパターンレビュー | パターン適用レビュー |
| [`csharp-docs.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-docs.prompt.md) | C# ドキュメント生成 | XML ドキュメント |
| [`csharp-async.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/csharp-async.prompt.md) | C# 非同期パターン | async/await ガイド |
| [`ef-core.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/ef-core.prompt.md) | Entity Framework Core | EF Core ガイド |
| [`aspnet-minimal-api-openapi.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/aspnet-minimal-api-openapi.prompt.md) | ASP.NET Minimal API + OpenAPI | Minimal API 設定 |

---

### Power Platform

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`power-bi-dax-optimization.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-bi-dax-optimization.prompt.md) | Power BI DAX 最適化 | 最適化された DAX |
| [`power-bi-model-design-review.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-bi-model-design-review.prompt.md) | Power BI モデルデザインレビュー | モデルレビュー |
| [`power-bi-performance-troubleshooting.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-bi-performance-troubleshooting.prompt.md) | Power BI パフォーマンストラブルシューティング | パフォーマンス改善 |
| [`power-bi-report-design-consultation.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-bi-report-design-consultation.prompt.md) | Power BI レポートデザイン相談 | デザイン推奨 |
| [`power-apps-code-app-scaffold.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-apps-code-app-scaffold.prompt.md) | Power Apps Code App スキャフォールド | Code App 雛形 |
| [`power-platform-mcp-connector-suite.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/power-platform-mcp-connector-suite.prompt.md) | Power Platform MCP コネクタスイート | MCP コネクタ |

---

### M365 Copilot / Agents

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`declarative-agents.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/declarative-agents.prompt.md) | Declarative Agents 作成 | エージェント定義 |
| [`mcp-create-declarative-agent.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/mcp-create-declarative-agent.prompt.md) | MCP Declarative Agent 作成 | MCP エージェント |
| [`mcp-create-adaptive-cards.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/mcp-create-adaptive-cards.prompt.md) | MCP Adaptive Cards 作成 | Adaptive Cards |
| [`mcp-deploy-manage-agents.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/mcp-deploy-manage-agents.prompt.md) | MCP エージェントのデプロイ・管理 | デプロイ手順 |
| [`typespec-create-agent.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/typespec-create-agent.prompt.md) | TypeSpec でエージェント作成 | TypeSpec 定義 |
| [`typespec-create-api-plugin.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/typespec-create-api-plugin.prompt.md) | TypeSpec で API プラグイン作成 | API プラグイン |
| [`typespec-api-operations.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/typespec-api-operations.prompt.md) | TypeSpec API オペレーション | API 操作定義 |
| [`create-agentsmd.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-agentsmd.prompt.md) | agents.md ファイル作成 | エージェント定義ファイル |
| [`finalize-agent-prompt.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/finalize-agent-prompt.prompt.md) | エージェントプロンプト最終化 | 最終調整されたプロンプト |

---

### Dataverse / Python

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`dataverse-python-quickstart.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dataverse-python-quickstart.prompt.md) | Dataverse Python クイックスタート | 入門コード |
| [`dataverse-python-production-code.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dataverse-python-production-code.prompt.md) | Dataverse Python 本番コード | 本番向けコード |
| [`dataverse-python-advanced-patterns.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dataverse-python-advanced-patterns.prompt.md) | Dataverse Python 高度なパターン | 上級パターン |
| [`dataverse-python-usecase-builder.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/dataverse-python-usecase-builder.prompt.md) | Dataverse Python ユースケースビルダー | ユースケース実装 |

---

### ユーティリティ・その他

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`remember.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/remember.prompt.md) | 記憶プロンプト | セッション間の記憶 |
| [`remember-interactive-programming.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/remember-interactive-programming.prompt.md) | インタラクティブプログラミング記憶 | REPL セッション記憶 |
| [`memory-merger.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/memory-merger.prompt.md) | メモリマージャー | 複数記憶の統合 |
| [`repo-story-time.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/repo-story-time.prompt.md) | リポジトリストーリータイム | リポジトリの歴史説明 |
| [`shuffle-json-data.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/shuffle-json-data.prompt.md) | JSON データシャッフル | ランダム化された JSON |
| [`convert-plaintext-to-md.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/convert-plaintext-to-md.prompt.md) | プレーンテキスト → Markdown 変換 | Markdown ファイル |
| [`update-markdown-file-index.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-markdown-file-index.prompt.md) | Markdown ファイルインデックス更新 | 目次更新 |
| [`mkdocs-translations.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/mkdocs-translations.prompt.md) | MkDocs 翻訳 | 多言語ドキュメント |
| [`next-intl-add-language.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/next-intl-add-language.prompt.md) | next-intl 言語追加 | 新言語サポート |
| [`editorconfig.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/editorconfig.prompt.md) | .editorconfig 生成 | エディター設定 |
| [`model-recommendation.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/model-recommendation.prompt.md) | モデル推奨 | AI モデル選択ガイド |
| [`boost-prompt.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/boost-prompt.prompt.md) | プロンプトブースト | プロンプト改善 |
| [`first-ask.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/first-ask.prompt.md) | 最初の質問 | 要件明確化の質問 |
| [`gen-specs-as-issues.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/gen-specs-as-issues.prompt.md) | 仕様を Issue として生成 | GitHub Issues |
| [`openapi-to-application-code.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/openapi-to-application-code.prompt.md) | OpenAPI → アプリケーションコード | コード生成 |
| [`devops-rollout-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/devops-rollout-plan.prompt.md) | DevOps ロールアウト計画 | デプロイ計画 |

---

### Copilot カスタマイズ

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`generate-custom-instructions-from-codebase.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/generate-custom-instructions-from-codebase.prompt.md) | コードベースからカスタム Instructions 生成 | Instructions ファイル |
| [`write-coding-standards-from-file.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/write-coding-standards-from-file.prompt.md) | ファイルからコーディング規約生成 | コーディング規約 |
| [`add-educational-comments.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/add-educational-comments.prompt.md) | 教育的コメント追加 | コメント付きコード |
| [`comment-code-generate-a-tutorial.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/comment-code-generate-a-tutorial.prompt.md) | コードコメント → チュートリアル生成 | チュートリアル |
| [`suggest-awesome-github-copilot-agents.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/suggest-awesome-github-copilot-agents.prompt.md) | おすすめ Agents 提案 | エージェント推奨 |
| [`suggest-awesome-github-copilot-collections.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/suggest-awesome-github-copilot-collections.prompt.md) | おすすめ Collections 提案 | コレクション推奨 |
| [`suggest-awesome-github-copilot-instructions.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/suggest-awesome-github-copilot-instructions.prompt.md) | おすすめ Instructions 提案 | Instructions 推奨 |
| [`suggest-awesome-github-copilot-prompts.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/suggest-awesome-github-copilot-prompts.prompt.md) | おすすめ Prompts 提案 | プロンプト推奨 |
| [`github-copilot-starter.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/github-copilot-starter.prompt.md) | GitHub Copilot スターター | 入門ガイド |
| [`prompt-builder.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/prompt-builder.prompt.md) | プロンプトビルダー | カスタムプロンプト作成 |

**[generate-custom-instructions-from-codebase.prompt.md](https://github.com/github/awesome-copilot/blob/main/prompts/generate-custom-instructions-from-codebase.prompt.md) の特徴:
- 既存コードベースを分析
- プロジェクト固有のパターンを抽出
- チーム向けカスタム Instructions を自動生成

---

### Structured Autonomy

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`structured-autonomy-generate.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/structured-autonomy-generate.prompt.md) | 構造化自律生成 | 生成されたコード |
| [`structured-autonomy-implement.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/structured-autonomy-implement.prompt.md) | 構造化自律実装 | 実装されたコード |
| [`structured-autonomy-plan.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/structured-autonomy-plan.prompt.md) | 構造化自律計画 | 計画ドキュメント |

---

### Linux トリアージ

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`arch-linux-triage.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/arch-linux-triage.prompt.md) | Arch Linux トリアージ | 問題診断 |
| [`centos-linux-triage.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/centos-linux-triage.prompt.md) | CentOS トリアージ | 問題診断 |
| [`debian-linux-triage.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/debian-linux-triage.prompt.md) | Debian トリアージ | 問題診断 |
| [`fedora-linux-triage.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/fedora-linux-triage.prompt.md) | Fedora トリアージ | 問題診断 |

---

### LLM 設定

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-llms.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-llms.prompt.md) | LLM 設定作成 | LLM 設定ファイル |
| [`update-llms.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-llms.prompt.md) | LLM 設定更新 | 更新された設定 |

---

### コンポーネントドキュメント

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`create-oo-component-documentation.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/create-oo-component-documentation.prompt.md) | OO コンポーネントドキュメント作成 | コンポーネントドキュメント |
| [`update-oo-component-documentation.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-oo-component-documentation.prompt.md) | OO コンポーネントドキュメント更新 | 更新されたドキュメント |
| [`update-specification.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/update-specification.prompt.md) | 仕様更新 | 更新された仕様 |

---

### アプリレビュー

| ファイル名 | 用途 | 出力 |
|-----------|------|------|
| [`apple-appstore-reviewer.prompt.md`](https://github.com/github/awesome-copilot/blob/main/prompts/apple-appstore-reviewer.prompt.md) | Apple App Store レビュー対応 | レビュー準備チェックリスト |

---

## まとめ

Prompts は **138 ファイル** あり、以下のカテゴリに分類されます：

| カテゴリ | ファイル数 | 主な用途 |
|---------|----------|---------|
| ドキュメント生成 | 約 15 | README, 仕様書, ADR |
| 計画・設計 | 約 15 | 実装計画, PRD, アーキテクチャ |
| MCP サーバー生成 | 約 12 | 各言語の MCP サーバー |
| テスト生成 | 約 15 | Jest, xUnit, NUnit, Playwright |
| SQL・データベース | 約 5 | SQL 最適化, PostgreSQL |
| コンテナ・Docker | 約 5 | Dockerfile 生成 |
| GitHub・CI/CD | 約 10 | Actions, Issues, PR |
| Azure | 約 5 | コスト最適化, 診断 |
| Spring Boot / Java | 約 10 | プロジェクト作成, リファクタリング |
| .NET | 約 10 | アップグレード, ベストプラクティス |
| Power Platform | 約 8 | Power BI, Power Apps |
| M365 Copilot | 約 10 | Declarative Agents |
| ユーティリティ | 約 20 | 変換, 記憶, 設定 |

プロジェクトの定型タスクに合わせて、必要な Prompts を `.github/prompts/` ディレクトリにコピーして活用してください。
