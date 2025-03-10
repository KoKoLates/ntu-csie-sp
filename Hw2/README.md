# HW2: PvP Championship
There are 8 players (`P0` - `P7`) in this championship. We use a simpler **Double Elimination Tournament** for this championship. Each battle has only two players, so there are 14 battles(`A` - `N`) in total to generate a champion.

In this homework, **you have to finish such a championship by writing 2 programs(`battle.c` and `player.c`)**. You don't have to customize your championship. Just follow the picture above to finish your programs.

## Player Status Structured Message (PSSM)
A structure to pass between processes. **You cannot modify the structure by yourself**, or TA's program may not work fine with your program.

```c
typedef enum {
    FIRE,
    GRASS,
    WATER
} Attribute;

typedef struct {
    int real_player_id;     // ID of the Real Player, an integer from 0 - 7
    int HP;                 // Healthy Point
    int ATK;                // Attack Power
    Attribute attr;         // Player's attribute
    char current_battle_id; //current battle ID
    int battle_ended_flag;  // a flag for validate if the battle is 
                            // the last round or not, 1 for yes, 0 for no
} Status;
```
Here we give you some hints about PSSM:
1. You will not modify real_player_id, ATK and attr after the PSSM's creation by real players. You can see them as const variables.
2. Only `battles` will modify the value of current_battle_id.
3. Only `battles` will modify the value of battle_ended_flag from 0 to 1.
4. Only `players` will modify the value of battle_ended_flag from 1 to 0.

## Reference
* [Assignment](https://hackmd.io/@UTGhost/H1Nk8CpMi)
* [Description Video](https://www.youtube.com/watch?v=mNVUvgWQezA)
