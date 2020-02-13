# ARM テンプレート - DevTest Labs

## 00-devtest-labs-all.json

DevTest Labs を作成し、テスト環境に必要な一連の Azure リソースを作成します。

- 01-devtest-labs-minimum.json
    - 最小限の DevTest Labs インスタンスを作成するテンプレート
- 02-vnet.json
    - 仮想ネットワークを作成し、DevTest Labs と関連付けるテンプレート
- 03-devtest-labs-vm-shutdown-schedule.json
    - DevTest Labs で作成する仮想マシンの自動シャットダウンの設定をするテンプレート
- 04-devtest-labs-artifacts.json
    - DevTest Labs の成果物を設定するテンプレート
- 05-resource-group-owner.json
    - 指定された ID をこのリソースグループの "所有者" に設定するテンプレート


### 作成する Azure リソース

- DevTest Labs
    - 自動シャットダウンスケジュール
    - 成果物
- ストレージアカウント
- Key Vault
- 仮想ネットワーク

### 必要なパラメータ

| パラメータ | 説明 |
| :------- | :------- |
| `name` | Azure リソースにつける基本となる名前。この名前にプレフィックスを付与して、各 Azure リソースを作成する |
| `location` | Azure リソースを作成するリージョン |
| `owner` | 作成する Azure リソースの所有者。有効なユーザーのメールアドレスであること |
| `ownerId` | Azure リソースの所有者のオブジェクト ID |
| `projectName` | 作成する Azure リソースに関連するプロジェクト名。主にコスト追跡などの管理用に用いる |
| `projectCode` | 作成する Azure リソースに関連するプロジェクトコード。主にコスト追跡などの管理用に用いる |
| `addressPrefix` | 仮想マシンなどが利用する、仮想ネットワークの CIDR |
| `time` | 自動シャットダウンをする時刻を 'HHmm' で指定する |
| `timeZoneId` | 自動シャットダウン時刻のタイムゾーンを指定する |

