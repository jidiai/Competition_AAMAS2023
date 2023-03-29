
# Competition_AAMAS2023
<img src="imgs/Jidi%20logo.png" width='300px'>  <img src="imgs/aamas2023logo.png" width='300px'>

This is the source code for [AAMAS 2023 Imperfect-information Card Game Competition](http://www.jidiai.cn/aamas_2023/) held by Jidi

This competition has three tracks:

- Track - 1: [Four-player No-limit Texas Hold'em Competition](http://www.jidiai.cn/compete_detail?compete=30)

- Track - 2: [Bridge Competition](http://www.jidiai.cn/compete_detail?compete=31)

- Track - 3: [Mahjong Competition](http://www.jidiai.cn/compete_detail?compete=32)

All three tracks start from **April 10th, 2023** to **May 15th, 2023**.

- Competition intro page: http://www.jidiai.cn/aamas_2023/

- Jidi tutorial: https://github.com/jidiai/ai_lib/tree/master/assets

- Competition game description: [games](docs/games.md)


## Quick Start

---
You can follow the following steps to run the demo

**Clone the repo**

```bash
git clone https://github.com/jidiai/Competition_AAMAS2023.git
cd Competition_AAMAS2023
```

**Build virtual environment**

```bash
python3 -m venv competition-venv
source competition-venv/bin/activate
python3 -m pip install -e .
```
or 
```bash
conda create -n competition-venv python==3.7.5  #or 3.8
conda activate competition-venv
```

**Install necessary dependencies**
```bash
pip install -r requirements.txt
```

**Run a game**
```bash
python run_log.py --env fourplayers_nolimit_texas_holdem
```
```bash
python run_log.py --env chessandcard-mahjong_v3
```
```bash
python run_log.py --env bridge
```

## Submission

In the `agent/` folder lies the ready-to-submit agents. We have provided an implementation of random agents. 
The `run_log.py` load these agents and run a game. The Jidi backend evaluation your submission in the same way.  
So make sure `run_log.py` raises no error before you submit your policies to the platform.







