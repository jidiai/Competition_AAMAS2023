# Index

*   [Four-player No-limit Texas Hold'em](games.md#fourplayers_nolimit_texas_holdem)
*   [Bridge](games.md#bridge)
*   [Mahjong](games.md#chessandcard-mahjong_v3)

The environments used in the competition are adopted from [**rlcard**](https://github.com/datamllab/rlcard) implementation. We only
modify the game rules slightly and add game rendering.


# fourplayers_nolimit_texas_holdem
<img src="../imgs/TexasHoldem_snapshot.jpg" width='300px'>

[**RLCard description**](https://github.com/datamllab/rlcard/blob/master/docs/games.md#no-limit-texas-holdem)

- The game core is the same as the *No-limit Texas Hold'em* environment
- We adopt the *AECEnv* and *.utils.wrappers* from the **pettingzoo** package
- Each game episode contains one game round and the payoff compute gain/loss of chips for each player
- Each player has access to observation every decision round, the *true* player (player making current decision in the game) has access to the current observation and the others receive *None*
- For the *true* player, the observation has shape:
```python
{"obs":{"observation": array, "action_mask": array},    #observation has shape [54,], action_mask has shape [6,]
 "is_new_episode": int,                                 # flag indicating a new episode
 "current_move_player": 'player_x',                     # player name of the true player
 "controlled_player_index": int,                        # index of me
 "controlled_player_name": string                       # player name of me
 }
```
- The game only consider action of the *true* player at each decision round
- If your algorithm output illegal action, the game will detect and correct it automatically with a random action


# bridge
<img src="../imgs/bridge_snapshot.png" width='300px'>

[**RLCard description**](https://github.com/datamllab/rlcard/blob/master/docs/games.md#bridge)

- For the *true* player, the observation has shape:
```python
{"obs":{"observation": array, "action_mask": array},    #observation has shape [573,], action_mask has shape [91,]
 "is_new_episode": int,                                 # flag indicating a new episode
 "current_move_player": 'player_x',                     # player name of the true player
 "controlled_player_index": int,                        # index of me
 "controlled_player_name": string                       # player name of me
 }
```
- Different from bridge in real life. The declarer and the dummy play their own hands. The dummy shows its hand to the other player and he can see declarer's hand to cooperate.
- The game only consider action of the *true* player at each decision round
- If your algorithm output illegal action, the game will detect and correct it automatically with a random action

# chessandcard-mahjong_v3
<img src="../imgs/Mahjong_snapshot.jpg" width='300px'>

[**RLCard description**](https://github.com/datamllab/rlcard/blob/master/docs/games.md#mahjong)

- For the *true* player, the observation has shape:
```python
{"obs":{"observation": array, "action_mask": array},    #observation has shape [6,34,4], action_mask has shape [38,]
 "is_new_episode": int,                                 # flag indicating a new episode
 "current_move_player": 'player_x',                     # player name of the true player
 "controlled_player_index": int,                        # index of me
 "controlled_player_name": string                       # player name of me
 }
```
- The game engine detech *Hu*(win condition) after each decision round.
- The game only consider action of the *true* player at each decision round
- If your algorithm output illegal action, the game will detect and correct it automatically with a random action
