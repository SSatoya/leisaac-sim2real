# LeIsaac-Sim2Real 🚀

[EN](../../../README.md) | JP

このリポジトリは、LeIsaacをフォークし、SO-101 アームを用いた Sim2Real 研究・検証用にカスタマイズしたものです。

https://github.com/user-attachments/assets/763acf27-d9a9-4163-8651-3ba0a6a185d7

本リポジトリは、SO101Leader（LeRobot
）を使った IsaacLab
 でのテレオペレーション機能、データ収集、データ変換、その後のポリシー学習を提供します。

- 🤖 IsaacLab で SO101Follower（および関連ロボット）を使用し、対応するテレオペレーション手法を提供します。

- 🔄 HDF5 形式のデータを LeRobot Dataset へ変換するスクリプトを提供します。

- 🧠 シミュレーションで収集したデータを使い、GR00T N1.5
 をファインチューニングし、実機へデプロイできます。今後さらに多くのポリシーに対応予定です。

# インストール📚
## 環境構築
以下の手順に従って，Isaac SimおよびIsaac Labをインストールします．
```bash
# Create and activate environment
conda create -n leisaac python=3.11
conda activate leisaac

# Install cuda-toolkit
conda install -c "nvidia/label/cuda-12.8.1" cuda-toolkit

# Install PyTorch
pip install -U torch==2.7.0 torchvision==0.22.0 --index-url https://download.pytorch.org/whl/cu128

# Install IsaacSim
pip install --upgrade pip
pip install "isaacsim[all,extscache]==5.1.0" --extra-index-url https://pypi.nvidia.com

# Install IsaacLab
sudo apt install cmake build-essential

cd leisaac/dependencies/IsaacLab
./isaaclab.sh --install

```
次に，leisaacの依存関係をインストールします．
```
cd ../..
pip install -e source/leisaac
```
## アセットのダウンロード
USDの例としてキッチンのUSDが配布されています．
[こちら](https://github.com/LightwheelAI/leisaac/releases/tag/v0.1.0)からダウンロード可能です．

ダウンロードは以下のディレクトリ構造になるように配置してください．
```
<assets>
├── robots/
│   └── so101_follower.usd
└── scenes/
    └── kitchen_with_orange/
        ├── scene.usd
        ├── assets
        └── objects/
            ├── Orange001
            ├── Orange002
            ├── Orange003
            └── Plate
```
# 使い方
## テレオペレーション
以下のスクリプトを実行してテレオペレーションを実行できます．
テレオペレーションは，`SO101LiderArm`/`keyboard`/`gamecontroller`の３つから選択できます．

```
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=so101leader \
    --port=/dev/ttyACM0 \
    --num_envs=1 \
    --device=cuda \
    --enable_cameras \
    --record \
    --dataset_file=./datasets/dataset.hdf5
```

WebRTCを使用して遠隔で操作したい場合は，スクリプトの先頭に`LIVESTREAM=2`をつけて実行してください．




# 謝辞 🙏

本プロジェクトは、Lightwheel AI の LeIsaac に基づいています。また、IsaacLab および LeRobot にも感謝いたします。