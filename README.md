Mahjong Fan Calculator Python
=====

README:[English](https://github.com/ailab-pku/PyMahjongGB/blob/master/README.md)|[中文](https://github.com/ailab-pku/PyMahjongGB/blob/master/README-zh.md)

```Python
from MahjongGB import MahjongFanCalculator

# 算番函数
((fanCount, fanName), ...) MahjongFanCalculator(
    pack = ((packType, tileCode, offer), ...),
    hand = (tileCode, ...),
    winTile = tileCode,
    flowerCount = int 0..8,
    isSelfDrawn = bool,
    is4thTile = bool,
    isAboutKong = bool,
    isWallLast = bool,
    seatWind = int 0..3,
    prevalentWind = int 0..3,
	[optional, default = False]verbose = bool)
```

- pack: The declared tiles. A tuple of tuples of three elements each:
        packType of "PENG"/"GANG"/"CHI" for PUNG, KONG and CHOW,
		tileCode (see details below), middle tile in case of CHOW,
		offer, 1, 2, 3 for player on left/opposite/right who offers this tile in case of PUNG and KONG, 1, 2, 3 for which tile is offered in case of CHOW.
- hand: The concealed tiles in hand. A tuple of tileCodes.
- winTile: The winning tile to make Mahjong.
- flowerCount: The number of the Flower and Season tiles.
- isSelfDrawn: Whether the winning tile is self-drawn.
- is4thTile: Whether the winning tile is the 4th tile.
- isAboutKong: Whether the winning is about Kong. If the player wins by other's discard, it is Robbing the Kong. Otherwise, if the player wins by self-drawn, it is Out with Replacement Tile.
- isWallLast: Whether the winning tile is the last one in tile wall. If self-drawn, it is Last Tile Draw. Otherwise, it is Last Tile Claim.
- seatWind: Seat wind. The number 0, 1, 2, 3 represent East, South, West, and North respectively.
- prevalentWind: Prevalent wind. The number 0, 1, 2, 3 represent East, South, West, and North respectively.
- verbose: Default to False. If set to True, return format is (fan_point, cnt, fan_name, fan_name_en) instead of (fan_count, fan_name).
- return: This function returns a tuple of tuples of two elements each: the fan count and fan name of each fan.

TileCode Table:
W1 ~ W9 for CHARACTERS,
T1 ~ T9 for BAMBOOS,
B1 ~ B9 for DOTS,
F1 ~ F4 for WINDS,
J1 ~ J3 for DRAGONS,
H1 ~ H8 for FLOWERS and SEASONS.