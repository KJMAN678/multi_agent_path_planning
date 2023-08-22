```sh
source .venv/bin/activate

# pip-tools による requirements.txt の作成

pip-compile requirements.in

# ライブラリのインストール

pip install -r requirements.txt

### Centralized Solutions

# 実行
python3 ./centralized/sipp/multi_sipp.py ./centralized/sipp/input.yaml ./centralized/sipp/output.yaml

# 作成されたGIFファイル
centralized/sipp/results/success.gif
centralized/sipp/results/failure.gif

# 可視化
python3 ./centralized/sipp/visualize_sipp.py ./centralized/sipp/input.yaml ./centralized/sipp/output.yaml

# Video 作成
python3 ./centralized/sipp/visualize_sipp.py ./centralized/sipp/input.yaml ./centralized/sipp/output.yaml --video 'sipp.mp4' --speed 1

# 作成された MP4 ファイル
sipp.mp4

### Conflict Based Search
# 実行
python3 ./centralized/cbs/cbs.py ./centralized/cbs/input.yaml ./centralized/cbs/output.yaml

# 作成されたGIFファイル
centralized/cbs/results/test_1.gif
centralized/cbs/results/test_2.gif
centralized/cbs/results/test_3.gif
centralized/cbs/results/test_4.gif

# 可視化
python3 ./centralized/visualize.py ./centralized/cbs/input.yaml ./centralized/cbs/output.yaml

### Post-Processing
python3 ./centralized/scheduling/minimize.py ./centralized/cbs/output.yaml ./centralized/scheduling/real_schedule.yaml

### Velocity obstacles
# 実行
python3 ./decentralized/decentralized.py -f ./decentralized/velocity_obstacle/velocity_obstacle.mp4 -m ./decentralized/velocity_obstacle

# 作成されたGIFファイル
.decentralized/velocity_obstacle/velocity_obstacle_1.gif
.decentralized/velocity_obstacle/velocity_obstacle_2.gif

### Nonlinear Model-Predictive Control
# 実行
python3 ./decentralized/decentralized.py -m nmpc
```
