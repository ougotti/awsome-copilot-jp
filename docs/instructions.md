# Instructions 一覧と活用ガイド

> [github/awesome-copilot](https://github.com/github/awesome-copilot) で公開されている **168 個の Instructions** を日本語で解説します。

## Instructions とは

Instructions は、特定のファイルパターン（例: `*.py`, `*.tsx`）に対して Copilot が従うべきコーディング規約やベストプラクティスを定義するファイルです。一度設定すれば、該当ファイルを編集するたびに**自動的に適用**されます。

### 設定方法

```
.github/
  instructions/
    python.instructions.md
    react.instructions.md
```

ファイル先頭の YAML フロントマターで適用対象を指定します：

```yaml
---
applyTo: "**/*.py"
---
```

---

## カテゴリ別 Instructions 一覧

### プログラミング言語

#### Python

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `python.instructions.md` | PEP 8/257 準拠、型ヒント必須、docstring 形式 | Python プロジェクト全般 |
| `python-mcp-server.instructions.md` | FastMCP を使った MCP サーバー開発ガイド | MCP サーバーを Python で構築 |
| `copilot-sdk-python.instructions.md` | GitHub Copilot SDK（Python）の使い方 | Copilot を組み込んだアプリ開発 |
| `langchain-python.instructions.md` | LangChain フレームワークの規約 | LLM アプリ開発 |
| `playwright-python.instructions.md` | Playwright（Python）のテスト規約 | E2E テスト |

**python.instructions.md の主なルール:**
- PEP 8 スタイルガイド（4 スペースインデント、79 文字制限）
- `typing` モジュールの型ヒント必須（`List[str]`, `Dict[str, int]` など）
- PEP 257 準拠の docstring
- エッジケース処理と例外ハンドリング
- クリティカルパスのテストケース作成

---

#### C# / .NET

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `csharp.instructions.md` | C# 14 / ASP.NET Core 10 のベストプラクティス | .NET 開発全般 |
| `csharp-ja.instructions.md` | C# 規約（日本語版） | 日本語チーム向け |
| `csharp-ko.instructions.md` | C# 規約（韓国語版） | 韓国語チーム向け |
| `csharp-mcp-server.instructions.md` | C# での MCP サーバー開発 | MCP サーバー構築 |
| `copilot-sdk-csharp.instructions.md` | Copilot SDK（C#）の使い方 | Copilot 組み込みアプリ |
| `dotnet-architecture-good-practices.instructions.md` | .NET アーキテクチャパターン | 大規模 .NET プロジェクト |
| `dotnet-framework.instructions.md` | .NET Framework（レガシー）規約 | レガシーシステム保守 |
| `dotnet-upgrade.instructions.md` | .NET バージョンアップ移行ガイド | フレームワーク移行 |
| `dotnet-maui.instructions.md` | .NET MAUI クロスプラットフォーム開発 | モバイル/デスクトップアプリ |
| `dotnet-maui-9-to-dotnet-maui-10-upgrade.instructions.md` | MAUI 9 → 10 移行 | MAUI アップグレード |
| `dotnet-wpf.instructions.md` | WPF デスクトップアプリ（MVVM） | Windows デスクトップ |
| `blazor.instructions.md` | Blazor コンポーネント開発 | .NET Web UI |
| `aspnet-rest-apis.instructions.md` | ASP.NET Core REST API 設計 | Web API 構築 |

**csharp.instructions.md の主なルール:**
- PascalCase（public）、camelCase（private）、インターフェースは `I` プレフィックス
- `== null` ではなく `is null` / `is not null` を使用
- Nullable 参照型を適切に実装
- パターンマッチングと switch 式を積極的に活用
- public API には `<example>` 付き XML ドキュメントコメント

---

#### Java

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `java.instructions.md` | Java 開発の基本規約（Records、Pattern Matching） | Java プロジェクト全般 |
| `java-mcp-server.instructions.md` | Java での MCP サーバー開発（Project Reactor） | MCP サーバー構築 |
| `java-11-to-java-17-upgrade.instructions.md` | Java 11 → 17 移行ガイド | Java バージョンアップ |
| `java-17-to-java-21-upgrade.instructions.md` | Java 17 → 21 移行（Virtual Threads） | Java バージョンアップ |
| `java-21-to-java-25-upgrade.instructions.md` | Java 21 → 25 移行（Class-File API） | Java バージョンアップ |
| `springboot.instructions.md` | Spring Boot 開発規約 | Spring Boot アプリ |
| `springboot-4-migration.instructions.md` | Spring Boot 4 への移行 | Spring Boot アップグレード |
| `quarkus.instructions.md` | Quarkus クラウドネイティブ Java | 軽量 Java マイクロサービス |
| `quarkus-mcp-server-sse.instructions.md` | Quarkus での MCP サーバー（SSE） | MCP + Quarkus |

**java.instructions.md の主なルール:**
- DTO には Java Records を使用（従来のクラスより簡潔）
- イミュータビリティ優先（`final` クラス/フィールド、`List.of()` / `Map.of()`）
- `Optional<T>` で null を回避
- Google Java Style Guide 準拠の命名規則
- `mvn clean install` または `./gradlew build` でビルド検証

**java-17-to-java-21-upgrade.instructions.md の主なルール:**
- **Virtual Threads（JEP 444）**: `Thread.ofVirtual()` で高スループット並行処理
- **Pattern Matching for switch（JEP 441）**: `when` 句でガード付きパターン
- **Sequenced Collections（JEP 431）**: `getFirst()`, `getLast()`, `reversed()`
- **Record Patterns（JEP 440）**: ネストした分解操作
- `finalize()` を Cleaner API または try-with-resources に移行

---

#### Go

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `go.instructions.md` | Go 開発の基本規約（Effective Go 準拠） | Go プロジェクト全般 |
| `go-mcp-server.instructions.md` | Go での MCP サーバー開発 | MCP サーバー構築 |
| `copilot-sdk-go.instructions.md` | Copilot SDK（Go）の使い方 | Copilot 組み込みアプリ |

**go.instructions.md の主なルール:**
- `package` 宣言の重複禁止（各ファイル 1 つのみ）
- インターフェースを受け取り、具象型を返す
- エラーは即座にチェック、`fmt.Errorf` で `%w` を使ってラップ
- `interface{}` の代わりに `any` を使用（Go 1.18+）
- `io.Reader` ストリームは 1 回限り読み取り可能

---

#### TypeScript / JavaScript

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `typescript-5-es2022.instructions.md` | TypeScript 5.x / ES2022 規約 | TypeScript プロジェクト全般 |
| `typescript-mcp-server.instructions.md` | TypeScript での MCP サーバー開発 | MCP サーバー構築 |
| `copilot-sdk-nodejs.instructions.md` | Copilot SDK（Node.js）の使い方 | Copilot 組み込みアプリ |
| `nodejs-javascript-vitest.instructions.md` | Vitest を使った Node.js テスト | Vite プロジェクトのテスト |

**typescript-5-es2022.instructions.md の主なルール:**
- `any` を避け、`unknown` + 型の絞り込みを使用
- 純粋な ES Modules（`require` / `module.exports` 禁止）
- `async/await` + try/catch + 構造化エラー
- kebab-case のファイル名（例: `user-session.ts`）
- シークレットはハードコードせず、ネットワーク呼び出しにはリトライ/バックオフを実装

---

#### Rust

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `rust.instructions.md` | Rust 開発規約（所有権、Result 型） | Rust プロジェクト全般 |
| `rust-mcp-server.instructions.md` | Rust での MCP サーバー開発（rmcp SDK） | MCP サーバー構築 |

**rust.instructions.md の主なルール:**
- 所有権移動より借用（`&T`）を優先
- `Result<T, E>` で回復可能なエラーを処理、ライブラリでは `unwrap()` 禁止
- `Debug`, `Clone`, `PartialEq`, `From`, `Default` トレイトを適切に実装
- `unsafe` は最小限に、必ずドキュメント化
- `cargo fmt`, `cargo clippy`, `cargo test` でコード品質を維持

---

#### その他の言語

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `ruby-on-rails.instructions.md` | Ruby on Rails 規約（Fat Model, Skinny Controller） | Rails アプリ開発 |
| `ruby-mcp-server.instructions.md` | Ruby での MCP サーバー開発 | MCP サーバー構築 |
| `php-symfony.instructions.md` | Symfony フレームワーク規約 | PHP Web 開発 |
| `php-mcp-server.instructions.md` | PHP での MCP サーバー開発 | MCP サーバー構築 |
| `kotlin-mcp-server.instructions.md` | Kotlin での MCP サーバー開発 | MCP サーバー構築 |
| `swift-mcp-server.instructions.md` | Swift での MCP サーバー開発 | MCP サーバー構築 |
| `dart-n-flutter.instructions.md` | Dart / Flutter 開発規約 | モバイルアプリ開発 |
| `scala2.instructions.md` | Scala 2 開発規約 | Scala プロジェクト |
| `clojure.instructions.md` | Clojure 開発規約 | Clojure プロジェクト |
| `r.instructions.md` | R 言語開発規約 | データ分析/統計 |
| `apex.instructions.md` | Salesforce Apex 開発規約 | Salesforce 開発 |
| `lwc.instructions.md` | Lightning Web Components 規約 | Salesforce UI 開発 |
| `coldfusion-cfc.instructions.md` | ColdFusion CFC 規約 | ColdFusion 開発 |
| `coldfusion-cfm.instructions.md` | ColdFusion CFM 規約 | ColdFusion 開発 |
| `powershell.instructions.md` | PowerShell スクリプト規約 | 自動化スクリプト |
| `powershell-pester-5.instructions.md` | Pester 5 テスト規約 | PowerShell テスト |
| `shell.instructions.md` | シェルスクリプト規約 | Bash/Sh スクリプト |
| `makefile.instructions.md` | Makefile 規約 | ビルド自動化 |

---

### Web フレームワーク

#### React / Next.js

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `reactjs.instructions.md` | React 19+ 開発規約（関数コンポーネント、Hooks） | React SPA 開発 |
| `nextjs.instructions.md` | Next.js 16+（App Router、Server Components） | Next.js フルスタック |
| `nextjs-tailwind.instructions.md` | Next.js + Tailwind CSS | スタイリング統合 |

**reactjs.instructions.md の主なルール:**
- 関数コンポーネント + Hooks パターンを基本に
- TypeScript で props、state、コンポーネント定義に型を付与
- `React.memo`, `useMemo`, `useCallback` は適切に使用（過剰使用を避ける）
- React Testing Library で振る舞いをテスト（実装詳細ではなく）
- セマンティック HTML + ARIA 属性 + キーボードナビゲーション

**nextjs.instructions.md の主なルール:**
- `app/` ディレクトリ（App Router）を使用、Server Components がデフォルト
- Server Component 内で `next/dynamic` + `{ ssr: false }` は使用禁止
- `unstable_cache` より Cache Components（`use cache` ディレクティブ）を優先
- Server Components から自身の Route Handlers を呼び出さない（`lib/` に共通ロジックを抽出）
- `NEXT_PUBLIC_` 変数はビルド時にインライン化される

---

#### Vue.js / Angular / Svelte

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `vuejs3.instructions.md` | Vue.js 3（Composition API、Pinia） | Vue アプリ開発 |
| `angular.instructions.md` | Angular（Standalone Components、Signals） | Angular 開発 |
| `svelte.instructions.md` | Svelte 5（Runes: $state, $derived, $effect） | Svelte アプリ開発 |
| `astro.instructions.md` | Astro フレームワーク | コンテンツ駆動サイト |

**vuejs3.instructions.md の主なルール:**
- Options API より Composition API + `<script setup>` を優先
- グローバル状態は Pinia（`defineStore`）、ローカル状態は `ref`/`reactive`
- `defineProps` と `defineEmits` で TypeScript 型付きコンポーネント
- `v-html` は避け、HTML 入力は必ずサニタイズ（XSS 対策）
- 機密トークンは `localStorage` ではなく HTTP-only Cookie に保存

**angular.instructions.md の主なルール:**
- Standalone Components をデフォルトに（モジュールは明示的に必要な場合のみ）
- Angular Signals（`signal()`, `computed()`, `effect()`）でリアクティブ状態管理
- Angular 19+ では `@Input()` の代わりに `input()`, `output()`, `viewChild()` 関数を使用
- OnPush 変更検出戦略でパフォーマンス向上
- グローバルエラーインターセプターを実装

**svelte.instructions.md の主なルール:**
- Svelte 5 Runes を使用: `$state()` でリアクティブ状態、`$derived()` で計算値
- 状態同期には `$effect()` より `$derived()` を優先（effect は副作用専用）
- SSR ではグローバル `$state` モジュールを避ける（リクエスト間データ漏洩防止）
- SvelteKit の `+page.server.ts` でサーバーサイドデータロード
- `{#snippet}` ブロックで再利用可能なテンプレートロジック

---

#### その他のフレームワーク

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `nestjs.instructions.md` | NestJS（DI、モジュール構成） | Node.js バックエンド |
| `tanstack-start-shadcn-tailwind.instructions.md` | TanStack Start + shadcn/ui + Tailwind | モダン React スタック |
| `tailwind-v4-vite.instructions.md` | Tailwind CSS v4 + Vite | スタイリング |
| `oqtane.instructions.md` | Oqtane フレームワーク | .NET CMS |
| `wordpress.instructions.md` | WordPress 開発規約 | WordPress サイト |

---

### インフラ・DevOps

#### Terraform / IaC

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `terraform.instructions.md` | Terraform 基本規約 | IaC 全般 |
| `terraform-azure.instructions.md` | Terraform for Azure | Azure インフラ |
| `terraform-sap-btp.instructions.md` | Terraform for SAP BTP | SAP クラウド |
| `generate-modern-terraform-code-for-azure.instructions.md` | Azure 向け最新 Terraform コード生成 | Azure IaC |
| `azure-verified-modules-terraform.instructions.md` | Azure Verified Modules（Terraform） | 検証済みモジュール |

**terraform.instructions.md の主なルール:**
- 最新の安定版 Terraform とプロバイダーを使用
- 認証情報は AWS Secrets Manager / SSM Parameter Store に保存（state ファイルに含めない）
- 機密変数には `sensitive = true` を設定
- 単一リソースのためにモジュールを作成しない（過剰な抽象化を避ける）
- `terraform fmt`, `terraform validate`, `tflint` でコード品質を維持
- `terraform-docs` でドキュメント生成

---

#### Kubernetes / コンテナ

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `kubernetes-manifests.instructions.md` | Kubernetes マニフェスト規約 | K8s デプロイ |
| `kubernetes-deployment-best-practices.instructions.md` | K8s デプロイのベストプラクティス | 本番環境デプロイ |
| `containerization-docker-best-practices.instructions.md` | Docker コンテナ化のベストプラクティス | コンテナ開発 |

**kubernetes-manifests.instructions.md の主なルール:**
- 標準ラベル: `app.kubernetes.io/name`, `app.kubernetes.io/instance`, `app.kubernetes.io/version`
- セキュリティ: non-root 実行、`readOnlyRootFilesystem: true`、全 capabilities drop
- リソース requests/limits を定義、本番では Guaranteed QoS
- liveness, readiness, startup probes を実装
- `kubectl apply --dry-run`, kubeconform, ポリシーバリデーター（OPA Conftest, Kyverno）でデプロイ前検証

**containerization-docker-best-practices.instructions.md の主なルール:**
- マルチステージビルドでビルド時/ランタイム依存を分離
- 最小限のベースイメージ（Alpine, distroless）でアタックサーフェスを削減
- non-root ユーザーでコンテナ実行
- `.dockerignore` で不要なビルドコンテキストを除外
- hadolint, Trivy でイメージスキャン

---

#### CI/CD

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `github-actions-ci-cd-best-practices.instructions.md` | GitHub Actions CI/CD 規約 | CI/CD パイプライン |
| `azure-devops-pipelines.instructions.md` | Azure DevOps Pipelines | Azure DevOps CI/CD |
| `devops-core-principles.instructions.md` | DevOps の基本原則 | DevOps 文化導入 |

**github-actions-ci-cd-best-practices.instructions.md の主なルール:**
- 説明的な `name` と適切な `on` トリガー、`fetch-depth: 1` で最適化
- `GITHUB_TOKEN` は最小権限、クラウド認証には OIDC を使用
- `hashFiles` と `restore-keys` でキャッシュ最適化
- 本番デプロイ前に包括的なテスト（unit, integration, E2E）
- ロールバック手順、自動ヘルスチェック、デプロイ承認を確立

---

#### Azure

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `bicep-code-best-practices.instructions.md` | Azure Bicep 規約 | Azure IaC |
| `azure-verified-modules-bicep.instructions.md` | Azure Verified Modules（Bicep） | 検証済みモジュール |
| `azure-functions-typescript.instructions.md` | Azure Functions（TypeScript） | サーバーレス |
| `azure-logic-apps-power-automate.instructions.md` | Logic Apps / Power Automate | ワークフロー自動化 |

**bicep-code-best-practices.instructions.md の主なルール:**
- lowerCamelCase で命名（変数、パラメーター、リソース）
- パラメーターはファイル先頭に配置、`@description` デコレーター付き
- `reference()` や `resourceId()` の代わりにシンボリック名でリソース参照
- `uniqueString()` で意味のある一意のリソース名を生成
- シークレットを outputs に含めない

---

### テスト

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `playwright-typescript.instructions.md` | Playwright（TypeScript）E2E テスト | ブラウザ自動テスト |
| `playwright-python.instructions.md` | Playwright（Python）E2E テスト | ブラウザ自動テスト |
| `playwright-dotnet.instructions.md` | Playwright（.NET）E2E テスト | ブラウザ自動テスト |

**playwright-typescript.instructions.md の主なルール:**
- アクセシビリティ優先のセレクター: `getByRole()`, `getByLabel()`（脆弱な CSS セレクターを避ける）
- 自動リトライ付きアサーション（`await` プレフィックス）
- Playwright 組み込みの自動待機を活用（ハードコードした wait を避ける）
- `test.step()` でインタラクションをグループ化
- `tests/` ディレクトリに `<feature>.spec.ts` 形式で保存

---

### セキュリティ・品質

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `security-and-owasp.instructions.md` | OWASP Top 10 ベースのセキュア コーディング | セキュリティ対策 |
| `performance-optimization.instructions.md` | パフォーマンス最適化ガイド | パフォーマンス改善 |
| `a11y.instructions.md` | アクセシビリティ（WCAG 2.2 Level AA） | アクセシビリティ対応 |
| `code-review-generic.instructions.md` | 汎用コードレビューガイドライン | コードレビュー |
| `self-explanatory-code-commenting.instructions.md` | 自己説明的なコードとコメント | コード可読性 |
| `object-calisthenics.instructions.md` | Object Calisthenics（コード品質練習） | コード品質向上 |

**security-and-owasp.instructions.md の主なルール:**
- 最小権限の原則、「デフォルト拒否」パターン
- データベースにはパラメータ化クエリのみ使用（SQL インジェクション対策）
- パスワードハッシュには Argon2, bcrypt、機密データ暗号化には AES-256
- シークレットは環境変数またはシークレット管理サービスから読み込み
- セッション Cookie に `HttpOnly`, `Secure`, `SameSite=Strict`、レート制限を実装

**a11y.instructions.md の主なルール:**
- WCAG 2.2 Level AA を満たす（可能な限り超える）
- 全インタラクティブ要素がキーボードナビゲーション可能、フォーカスインジケーター表示
- テキストコントラスト比 4.5:1 以上（大きいテキストは 3:1）
- 適切なセマンティクス（name, role, value, states, properties）とランドマーク使用
- フォーム要素にラベル、必須フィールドには `aria-required="true"`

---

### データベース

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `mongo-dba.instructions.md` | MongoDB DBA 規約 | MongoDB 管理 |
| `ms-sql-dba.instructions.md` | SQL Server DBA 規約 | SQL Server 管理 |
| `sql-sp-generation.instructions.md` | SQL ストアドプロシージャ生成 | DB 開発 |

---

### データ分析・AI

#### Dataverse / Python

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `dataverse-python.instructions.md` | Dataverse Python SDK 概要 | Dataverse 連携 |
| `dataverse-python-sdk.instructions.md` | SDK 詳細 | SDK 活用 |
| `dataverse-python-authentication-security.instructions.md` | 認証とセキュリティ | セキュア接続 |
| `dataverse-python-modules.instructions.md` | モジュール構成 | モジュール理解 |
| `dataverse-python-api-reference.instructions.md` | API リファレンス | API 活用 |
| `dataverse-python-best-practices.instructions.md` | ベストプラクティス | 品質向上 |
| `dataverse-python-error-handling.instructions.md` | エラーハンドリング | エラー処理 |
| `dataverse-python-file-operations.instructions.md` | ファイル操作 | ファイル管理 |
| `dataverse-python-pandas-integration.instructions.md` | Pandas 統合 | データ分析 |
| `dataverse-python-performance-optimization.instructions.md` | パフォーマンス最適化 | 性能改善 |
| `dataverse-python-testing-debugging.instructions.md` | テストとデバッグ | 品質保証 |
| `dataverse-python-advanced-features.instructions.md` | 高度な機能 | 上級活用 |
| `dataverse-python-agentic-workflows.instructions.md` | エージェントワークフロー | AI ワークフロー |
| `dataverse-python-real-world-usecases.instructions.md` | 実世界ユースケース | 実践活用 |

---

### Power Platform

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `power-apps-canvas-yaml.instructions.md` | Power Apps Canvas YAML 形式 | Canvas アプリ |
| `power-apps-code-apps.instructions.md` | Power Apps Code Apps | コードベースアプリ |
| `power-platform-connector.instructions.md` | Power Platform カスタムコネクタ | コネクタ開発 |
| `power-platform-mcp-development.instructions.md` | Power Platform MCP 開発 | MCP 連携 |

#### Power BI

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `power-bi-custom-visuals-development.instructions.md` | カスタムビジュアル開発 | ビジュアル作成 |
| `power-bi-data-modeling-best-practices.instructions.md` | データモデリング | モデル設計 |
| `power-bi-dax-best-practices.instructions.md` | DAX ベストプラクティス | 計算式作成 |
| `power-bi-devops-alm-best-practices.instructions.md` | DevOps / ALM | CI/CD for Power BI |
| `power-bi-report-design-best-practices.instructions.md` | レポートデザイン | レポート作成 |
| `power-bi-security-rls-best-practices.instructions.md` | セキュリティ / RLS | 行レベルセキュリティ |

---

### Power Component Framework (PCF)

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `pcf-overview.instructions.md` | PCF 概要 | PCF 入門 |
| `pcf-api-reference.instructions.md` | API リファレンス | API 活用 |
| `pcf-best-practices.instructions.md` | ベストプラクティス | 品質向上 |
| `pcf-code-components.instructions.md` | コードコンポーネント | コンポーネント開発 |
| `pcf-canvas-apps.instructions.md` | Canvas アプリ統合 | Canvas 連携 |
| `pcf-model-driven-apps.instructions.md` | Model-Driven アプリ統合 | MDA 連携 |
| `pcf-power-pages.instructions.md` | Power Pages 統合 | Web ポータル |
| `pcf-fluent-modern-theming.instructions.md` | Fluent / モダンテーマ | スタイリング |
| `pcf-react-platform-libraries.instructions.md` | React プラットフォームライブラリ | React 連携 |
| `pcf-dependent-libraries.instructions.md` | 依存ライブラリ | ライブラリ管理 |
| `pcf-manifest-schema.instructions.md` | マニフェストスキーマ | 設定ファイル |
| `pcf-tooling.instructions.md` | ツール | 開発ツール |
| `pcf-events.instructions.md` | イベント | イベントハンドリング |
| `pcf-limitations.instructions.md` | 制限事項 | 制約の理解 |
| `pcf-sample-components.instructions.md` | サンプルコンポーネント | 学習 |
| `pcf-community-resources.instructions.md` | コミュニティリソース | 情報収集 |
| `pcf-alm.instructions.md` | ALM（ライフサイクル管理） | DevOps |

---

### Linux ディストリビューション

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `arch-linux.instructions.md` | Arch Linux 規約 | Arch 環境 |
| `centos-linux.instructions.md` | CentOS 規約 | CentOS 環境 |
| `debian-linux.instructions.md` | Debian 規約 | Debian 環境 |
| `fedora-linux.instructions.md` | Fedora 規約 | Fedora 環境 |

---

### Copilot / MCP / AI 開発

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `agents.instructions.md` | Agent ファイルの書き方 | Agent 作成 |
| `agent-skills.instructions.md` | Agent Skills 定義 | スキル作成 |
| `instructions.instructions.md` | Instructions ファイルの書き方 | Instructions 作成 |
| `prompt.instructions.md` | Prompt ファイルの書き方 | Prompt 作成 |
| `collections.instructions.md` | Collections ファイルの書き方 | Collection 作成 |
| `memory-bank.instructions.md` | Memory Bank（セッション間記憶） | 長期記憶管理 |
| `copilot-thought-logging.instructions.md` | Copilot 思考ログ | デバッグ |
| `mcp-m365-copilot.instructions.md` | M365 Copilot MCP 連携 | M365 統合 |
| `typespec-m365-copilot.instructions.md` | TypeSpec for M365 Copilot | API 定義 |
| `declarative-agents-microsoft365.instructions.md` | M365 Declarative Agents | M365 エージェント |
| `ai-prompt-engineering-safety-best-practices.instructions.md` | プロンプトエンジニアリング安全規約 | 安全な AI 活用 |
| `taming-copilot.instructions.md` | Copilot の制御 | Copilot 活用 |
| `genaiscript.instructions.md` | GenAIScript 規約 | AI スクリプト |

**memory-bank.instructions.md の主なルール:**
- セッションリセット後は Memory Bank に完全に依存（必須ファイルを毎回読み込む）
- 必須コアファイル: `projectbrief.md`, `productContext.md`, `activeContext.md`, `systemPatterns.md`, `techContext.md`, `progress.md`
- 各タスクに専用の Markdown ファイルを作成（元のリクエスト、思考プロセス、実装計画、進捗ログを記録）
- パターン発見、変更実装、明示的な更新リクエスト時に Memory Bank を更新

---

### ワークフロー・プロセス

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `spec-driven-workflow-v1.instructions.md` | 仕様駆動ワークフロー | 仕様ファースト開発 |
| `task-implementation.instructions.md` | タスク実装ガイド | タスク管理 |
| `tasksync.instructions.md` | タスク同期 | チーム協調 |
| `update-code-from-shorthand.instructions.md` | 短縮形からコード更新 | コード生成 |
| `update-docs-on-code-change.instructions.md` | コード変更時のドキュメント更新 | ドキュメント同期 |
| `localization.instructions.md` | ローカライゼーション | 多言語対応 |

---

### 開発環境・ツール

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `devbox-image-definition.instructions.md` | Devbox イメージ定義 | 開発環境構築 |
| `vsixtoolkit.instructions.md` | VSIX Toolkit | VS Code 拡張開発 |
| `cmake-vcpkg.instructions.md` | CMake + vcpkg | C++ ビルド |
| `html-css-style-color-guide.instructions.md` | HTML/CSS スタイル・カラーガイド | Web デザイン |
| `markdown.instructions.md` | Markdown 規約 | ドキュメント作成 |

---

### VS Code / Joyride

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `joyride-user-project.instructions.md` | Joyride ユーザープロジェクト | VS Code 自動化 |
| `joyride-workspace-automation.instructions.md` | Joyride ワークスペース自動化 | ワークスペース管理 |
| `codexer.instructions.md` | Codexer 規約 | コード生成 |

---

### レビュー・移行

| ファイル名 | 概要 | 活用場面 |
|-----------|------|---------|
| `gilfoyle-code-review.instructions.md` | Gilfoyle スタイルコードレビュー | 厳格なレビュー |
| `convert-cassandra-to-spring-data-cosmos.instructions.md` | Cassandra → Spring Data Cosmos 移行 | DB 移行 |
| `convert-jpa-to-spring-data-cosmos.instructions.md` | JPA → Spring Data Cosmos 移行 | DB 移行 |

---

## まとめ

Instructions は **168 ファイル** あり、以下のカテゴリに分類されます：

| カテゴリ | ファイル数 | 主な内容 |
|---------|----------|---------|
| プログラミング言語 | 約 40 | Python, C#, Java, Go, TypeScript, Rust 等 |
| Web フレームワーク | 約 15 | React, Next.js, Vue, Angular, Svelte 等 |
| インフラ・DevOps | 約 20 | Terraform, Kubernetes, Docker, CI/CD |
| テスト | 約 5 | Playwright (各言語版) |
| セキュリティ・品質 | 約 10 | OWASP, アクセシビリティ, パフォーマンス |
| データベース | 約 5 | MongoDB, SQL Server |
| Power Platform | 約 25 | Power BI, PCF, Power Apps |
| MCP サーバー開発 | 約 10 | 各言語の MCP SDK |
| Copilot SDK | 約 5 | Python, C#, Go, Node.js |
| その他 | 約 30 | ワークフロー, ツール, 環境設定 |

チームのニーズに合わせて、必要な Instructions を `.github/instructions/` ディレクトリにコピーして活用してください。
