# Extra test maps for UNSW Battlecode 2026

156 unofficial maps for testing a bot on layouts it has not seen. A generator made them from the official maps of the `unswbc` toolkit: new sizes and layouts of the official designs, edited copies of the official maps themselves, and maps built round one situation a bot has to handle. Every map loads in the official engine, is mirror-symmetric (beds, kelp, portals and starters) and was played on the engine before it was kept. The organisers had no part in them.

Play on one with the official toolkit (`pip install unswbc`):

    unswbc run fortress/fortress_maze_40x20.map path/to/bot_a path/to/bot_b --seed 1

* `gallery.html` draws every map, the family maps and re-issues beside the official maps they come from. Download it (or clone this folder) and open it in a browser.
* `manifest.csv` has one row per map: what it tests, the official maps it is patterned on, its statistics, the playability check and the generator command that rebuilds it (the generator is not in this folder).
* A tag such as **SIDE(B)** after a description comes from a mirror match: one bot against itself on four seeds. It means the same side won all four games. Team A's dragons move first each round, so on that map the layout or the turn order may favour a side (a fair map does this by chance one time in eight).

| Folder | Maps | Patterned on | What the pattern is |
|---|---|---|---|
| `fortress/` | 15 | Stronghold, Trauma, Maze, weakhold | An open home field at each end behind a kelp wall, fountains only in 1-wide pockets, and a middle that is bare (Stronghold), a maze with small rooms of beds (Trauma), a dense 1-wide maze (Maze) or mazes round an open court (weakhold). |
| `corridors/` | 7 | Prisoners Dilemma, Autarky | One long dragon per team lies in a column down the middle of the map. The column is 1-wide at its ends, with two fountains in front of the head and two behind the tail, so the dragon starts with two or three free tiles; sealed 3x3 rooms are entered only by a portal whose gate is in the other half of the map. |
| `cells/` | 9 | Portals | A staggered grid of 2x2 cells of rich beds. A cell opens only through a portal edge inside it, the gate to it stands beside the same cell in the other half, some cells are split so half their beds are decoys, and the two halves of the map never touch. |
| `stripes/` | 6 | Stripes | Bands three rows deep that run right round the map (the sides wrap), joined by one gap near each end of every wall, with trick cells along them: portal edges side by side, a closet entered from the band below, a booth that swaps sides, sealed decoy beds. |
| `lanes/` | 7 | Devil | 1-wide lanes with a fountain at each end (they wrap top to bottom) between 2-wide strips of thin beds; the only ways across are a narrow band through the middle and two short gaps beside the centre strip. |
| `arena/` | 10 | Colosseum, Default Small, Default | The classic maps, where every tile is a bed. A walled arena of richer beds inside a ring three tiles wide, with portals that carry a dragon straight across it; homes that are quarters of the map with a single exit; or Default's nine sealed cells joined into one chain by portals. |
| `tower/` | 5 | Tower Defense | Each team starts inside a keep wrapped in rings of 1-wide corridor (the official keep, as a stamp); the food worth having is a block of cells in the middle, a long way out. |
| `picture/` | 9 | Trophy, Queen Of Spades | A wrap map of thin beds round one big figure drawn in kelp. Mirrored maps follow Trophy (queens in side chambers, richer beds inside the rim, a portal down the centre line); rotated maps follow Queen Of Spades (a playing card: a frame of kelp inside a ring of thin beds, sealed figures and corner boxes full of beds nobody can reach, and a crown of rich beds whose only way in is a portal from the other team's corner). |
| `islands/` | 8 | Islands, Schooltime | No rooms and no corridors: hundreds of short strokes of kelp (two in five a single edge, a few long hooked walls) with beds in the nooks and a few portals. The school maps follow Schooltime: the queen coiled in a sealed 2x2 box, the official map's own fish (outlines full of beds with a one-edge mouth and a sealed eye), sealed 2x2 boxes, long outlines, a bed of thin beds along the bottom. |
| `continent/` | 6 | Australia, Around UNSW | The two 64x64 maps added for the Sprint are one drawing made twice: a copy per team, the second turned round, meeting along the middle of a wrap map. Continent maps follow Australia (five states behind straight borders, the starters in the western one and one posted beside the enemy's home, single beds on a lattice, a sealed island behind a portal); campus maps follow Around UNSW (a walled ring round the home, a length-10 dragon lying between two fountain pockets, portals set into the coast). |
| `variants/` | 40 | every official map | Official maps edited the way the organisers edit them between releases (beds re-rated, kelp added, a different starter made queen, portals added or removed), and official maps with team B mirrored the other way (`resym`). |
| (this folder) | 34 | motifs from several maps | The behaviour suite: each map is built round one bot behaviour (queen safety, doomed starts, the unit limit, tiny maps, map-size boundaries, ...). |

## fortress/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `fortress_keeps_40x20` | 40x20 | xy | Stronghold at 40x20: each home is sealed and opens only through the keep's two portals; five fountains in the keep's dead end. |
| `fortress_keeps_y_56x28` | 56x28 | y | Stronghold bigger, mirrored instead of rotated, three starters: both keeps on the top edge, a 30-column bare middle. |
| `fortress_rooms_48x24_s1` | 48x24 | xy | Trauma's frame (sealed home, keep, home portal that comes out past the axis) with a new maze of bed rooms in the middle. |
| `fortress_rooms_48x24_s2` | 48x24 | xy | A second maze of rooms in Trauma's frame: same statistics, different routes. |
| `fortress_rooms_y_56x24` | 56x24 | y | Trauma's frame mirrored and wider: the two home portals come out side by side just past the axis. |
| `fortress_rooms_40x20` | 40x20 | xy | Trauma's frame at 40x20: the keep takes half of the space between home and axis, so the maze is short and tight. |
| `fortress_maze_48x24_s1` | 48x24 | xy | Maze's frame (bed block in the home, five doors in the home wall) with a new 1-wide maze: 30 fountains in dead ends of three. |
| `fortress_maze_48x24_s2` | 48x24 | xy | A second maze at the official size: pocket mining and reverse-outs with different dead ends. |
| `fortress_maze_40x20` | 40x20 | xy | Maze at 40x20: the same density of corridors, fountains and portals on 800 tiles. |
| `fortress_maze_y_56x28` | 56x28 | y | Maze bigger and mirrored: the queens face each other along one row instead of across the diagonal. |
| `fortress_maze_64x32` | 64x32 | xy | Maze at the width limit: 2,048 tiles of 1-wide corridor, turn time with many dragons in a maze. |
| `fortress_weak_40x15_s1` | 40x15 | xy | weakhold's frame (5-wide homes, starters lying along them, maze bands, open court) with new maze bands. |
| `fortress_weak_40x15_s2` | 40x15 | xy | A second pair of maze bands in weakhold's frame. |
| `fortress_weak_48x18` | 48x18 | xy | weakhold wider and taller: a larger court between the maze bands. |
| `fortress_weak_y_36x14` | 36x14 | y | weakhold smaller and mirrored: both rich rooms of the court end up on the top edge. |

## corridors/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `corridors_40x16` | 40x16 | xy | Prisoners Dilemma wider: four more columns of bare home on each side before the rooms. **SIDE(B)** |
| `corridors_32x20` | 32x20 | xy | Prisoners Dilemma taller: the long dragon is length 15, so the reverse split matters more. **SIDE(B)** |
| `corridors_44x18` | 44x18 | xy | Prisoners Dilemma's layout at 44x18, between the two official sizes. |
| `corridors_y_36x16` | 36x16 | y | Prisoners Dilemma mirrored: the long dragons lie side by side and head for the same end. **SIDE(B)** |
| `corridors_tall_16x32` | 16x32 | xy | Prisoners Dilemma itself, turned on its side (teams at top and bottom): any change in results from the official map is the bot favouring a direction. **SIDE(B)** |
| `corridors_wide_60x20` | 60x20 | xy | Autarky's layout bigger: four rooms a side, a length-16 long dragon, six starters, dotted thin beds. |
| `corridors_wide_y_58x18` | 58x18 | y | Autarky's layout mirrored: every gate leads to the room straight across the map. |

## cells/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `cells_32x16_s1` | 32x16 | xy | Portals' size and statistics with the cell kinds dealt differently: which gates are worth taking has to be worked out again. |
| `cells_32x16_s2` | 32x16 | xy | A second deal of whole, split and decoy cells at the official size. |
| `cells_32x16_s3` | 32x16 | xy | A third deal at the official size. |
| `cells_40x20` | 40x20 | xy | Portals at 40x20: 20 cells a side, ten of them live (the official portal count), the rest decoys. |
| `cells_24x12` | 24x12 | xy | Portals at 24x12: two columns of cells and a short fountain lane. |
| `cells_48x16` | 48x16 | xy | Portals wider: five columns of cells between home and lane. |
| `cells_y_36x16` | 36x16 | y | Portals mirrored: the two fountain lanes lie side by side behind one straight wall. |
| `cells_joined_32x16` | 32x16 | xy | Portals with the wall between the two fountain lanes opened: one 1-wide passage of eight fountains joins the halves. **SIDE(B)** |
| `cells_tall_16x32` | 16x32 | xy | Portals turned on its side with a new deal of cells: teams at top and bottom. |

## stripes/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `stripes_36x12` | 36x12 | xy | Stripes longer: the same four bands, twelve more columns between the cells and the starters. |
| `stripes_24x18` | 24x18 | xy | Stripes with six bands: three starters a side, and the teams' bands touch along the middle wall. |
| `stripes_48x12` | 48x12 | xy | Stripes twice as long: a full lap of a band is 48 steps. |
| `stripes_32x24` | 32x24 | xy | Stripes with eight bands and four starters a side. |
| `stripes_30x18` | 30x18 | xy | Stripes with six bands at 30 columns. |
| `stripes_tall_12x24` | 12x24 | xy | Stripes itself, turned on its side: the bands run top to bottom and wrap there. |

## lanes/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `lanes_xy_32x16` | 32x16 | xy | Devil rotated instead of mirrored: the crossing band is two rows on the centre line. |
| `lanes_38x16` | 38x16 | y | Devil with one more lane and strip on each side. |
| `lanes_44x20` | 44x20 | y | Devil with two more lanes a side and four more rows: longer lanes, the same 3-row band. |
| `lanes_26x12` | 26x12 | y | Devil at 26x12: two lanes a side, contact through the band inside a dozen rounds. |
| `lanes_32x24` | 32x24 | y | Devil taller: 24-row lanes, so a dragon committed to a lane is committed for a long time. |
| `lanes_x_16x32` | 16x32 | x | Devil itself, turned on its side, which makes it SYMMETRY x (no official map uses that): the lanes run left to right. |
| `lanes_xy_44x18` | 44x18 | xy | Devil rotated at 44x18. **SIDE(A)** |

## arena/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `arena_20x20` | 20x20 | xy | Colosseum at 20x20: a 14x14 arena, five tiles of kelp at each end of every arena wall. |
| `arena_24x16` | 24x16 | xy | Colosseum wider than tall: an 18x10 arena. |
| `arena_32x32` | 32x32 | xy | Colosseum at 32x32 with two starters: a 26x26 arena on 1,024 tiles. **SIDE(B)** |
| `arena_tall_16x24` | 16x24 | xy | Colosseum taller than wide: the home strips are at the left and right ends. |
| `quadrants_20x20` | 20x20 | xy | Default Small at 20x20: 9x9 home quarters with their single exit, staircases four steps long. |
| `quadrants_24x24` | 24x24 | xy | Default Small at 24x24. |
| `quadrants_32x32` | 32x32 | xy | Default Small at 32x32 with three starters: the home's one exit is 15 tiles from the queen. |
| `default_28x28` | 28x28 | xy | Default at 28x28: the same room, bars and chain of nine sealed cells joined by portals, on three quarters of the tiles. |
| `default_40x40` | 40x40 | xy | Default at 40x40 with 6x6 cells: 1,600 tiles of the thinnest beds. |
| `default_48x48_3` | 48x48 | xy | Default at 48x48 with 8x8 cells and three starters instead of four. |

## tower/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `tower_40x16` | 40x16 | xy | Tower Defense wider: six columns of open water between each tower and the block in the middle. |
| `tower_32x20` | 32x20 | xy | Tower Defense taller: four open rows under each tower, the block centred. **SIDE(B)** |
| `tower_y_36x16` | 36x16 | y | Tower Defense mirrored: both towers on the top edge, both gardens on the bottom. |
| `tower_36x18` | 36x18 | xy | Tower Defense at 36x18 with three length-2 starters (none can split until it has eaten). |
| `tower_tall_16x32` | 16x32 | xy | Tower Defense itself, turned on its side: the towers are top-left and bottom-right as before, the way out now leads down. **SIDE(A)** |

## picture/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `picture_heart_25x25` | 25x25 | y | Trophy's layout with a heart: queens in side chambers facing it, richer beds inside the rim, a portal down the centre line. **SIDE(A)** |
| `picture_diamond_25x27` | 25x27 | y | Trophy's layout with a diamond: the figure's points leave wide open water at the corners. **SIDE(A)** |
| `picture_club_27x27` | 27x27 | y | Trophy's layout with a club: three lobes and a stem, so the inside has narrow necks. |
| `picture_star_29x27` | 29x27 | y | Trophy's layout with a star: thin arms that are dead ends from inside. |
| `picture_heart_44x44` | 44x44 | y | A heart drawn twice the size on 44x44: 1,936 tiles, nearly all thin beds. |
| `picture_spade_27x37` | 27x37 | xy | Queen Of Spades' card redrawn: a kelp frame inside a ring of thin beds, two sealed spades and corner boxes of decoy beds, the crown of rich beds reached only by the portal in the other team's corner. |
| `picture_club_25x35` | 25x35 | xy | Queen Of Spades' card at the official size with clubs. |
| `picture_fish_48x24` | 48x24 | xy | Queen Of Spades' card on a wide map, with a fish: the teams are left and right instead of top and bottom. |
| `picture_diamond_40x26` | 40x26 | xy | Queen Of Spades' card on a wide map with diamonds. |

## islands/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `islands_56x40_s1` | 56x40 | y | Islands' size and statistics with new kelp: the home box with four corner fountains, five starters, six portal pairs. |
| `islands_56x40_s2` | 56x40 | y | A second scatter at the official size. |
| `islands_48x32` | 48x32 | y | Islands at 48x32. |
| `islands_xy_40x28` | 40x28 | xy | Islands rotated instead of mirrored, at 40x28. |
| `islands_64x40` | 64x40 | y | Islands at the width limit. |
| `school_60x40_s1` | 60x40 | y | Schooltime's size and start: the queen is an L4 coiled in a sealed 2x2 box with one bed (she must split to live), two more coils in the open, the official map's three fish (beds behind a one-edge mouth). **SIDE(B)** |
| `school_60x40_s2` | 60x40 | y | A second school at the official size: the fish dealt to other places, other outlines. |
| `school_48x32` | 48x32 | y | Schooltime's start at 48x32, with two fish. **SIDE(A)** |

## continent/

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `continent_64x64_s1` | 64x64 | xy | Australia's pattern: a drawing per team meeting in the middle, five states, eight starters at home and one posted beside the enemy's home, lattice beds, an island of 1-10 beds behind a portal. |
| `continent_64x64_s2` | 64x64 | xy | A second drawing at 64x64: other coasts, borders and starting places. |
| `continent_56x56` | 56x56 | xy | The same pattern at 56x56. **SIDE(B)** |
| `campus_64x64_s1` | 64x64 | xy | Around UNSW's pattern: a walled ring round the home with a chequered yard, twelve fountains a side in dead ends, ten starters, the length-10 one lying with its head in a fountain pocket (it cannot move forward), portals set into the coast. |
| `campus_64x64_s2` | 64x64 | xy | A second campus at 64x64. |
| `campus_48x48` | 48x48 | xy | The campus pattern at 48x48: ten starters in a much smaller drawing. |

## variants/ (re-issued official maps)

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `default_var1_portalsadd_gaps` | 32x32 | xy | Default as the organisers might re-issue it: portal added between (17, 18) and (6, 6) (and its mirror); 1-769 beds become 1-2559. |
| `default_var2_kelp_queen` | 32x32 | xy | Default as the organisers might re-issue it: 2 short kelp walls added (and their mirrors); starter 4 (length 4) is now the queen instead of the length-4 one. |
| `trophy_var3_gaps_fountains` | 25x25 | y | Trophy as the organisers might re-issue it: 5-30 beds become 2-15; 1-1000 beds become 1-2559; fountains added at (11, 23) and (0, 4) (and their mirrors). |
| `trophy_var1_portalsadd_thin` | 25x25 | y | Trophy as the organisers might re-issue it: portal added between (9, 19) and (17, 16) (and its mirror); 160 of the 489 1-1000 beds silenced. |
| `queen_of_spades_var1_portalsadd_kelp` | 25x35 | xy | Queen Of Spades as the organisers might re-issue it: portal added between (20, 1) and (24, 9) (and its mirror); 1 short kelp walls added (and their mirrors). **SIDE(B)** |
| `devil_var1_fountains_thin` | 32x16 | y | Devil as the organisers might re-issue it: 9 fountain pairs moved 2-5 steps; 20 of the 64 1-300 beds silenced. **SIDE(A)** |
| `dilemma_var1_queen_fountains` | 32x16 | xy | Prisoners Dilemma as the organisers might re-issue it: starter 3 (length 3) is now the queen instead of the length-3 one; 4 fountain pairs moved 2-5 steps. |
| `autarky_var1_gaps_portalsdel` | 54x18 | xy | Autarky as the organisers might re-issue it: 1-500 beds become 1-1000; portal 0 and 1 removed (was (4, 7) <-> (49, 13)). **SIDE(B)** |
| `portals_var1_fountains_portalsadd` | 32x16 | xy | Portals as the organisers might re-issue it: 4 fountain pairs moved 2-5 steps; portal added between (1, 4) and (10, 8) (and its mirror). **SIDE(A)** |
| `trauma_var1_fountains_doors` | 48x24 | xy | Trauma as the organisers might re-issue it: 6 fountain pairs moved 2-5 steps; 3 kelp edges opened (and their mirrors), e.g. at (12, 3). |
| `schooltime_var1_gaps_portalsadd` | 60x40 | y | Schooltime as the organisers might re-issue it: 20-200 beds become 40-400; 20-80 beds become 10-40; portal added between (39, 25) and (17, 30) (and its mirror). **SIDE(A)** |
| `slithery_fight_var1_thin_fountains` | 63x27 | xy | Slithery Fight as the organisers might re-issue it: 54 of the 164 1-2559 beds silenced; 11 fountain pairs moved 2-5 steps. |
| `maze_var1_fountains_portalsdel` | 48x24 | xy | Maze as the organisers might re-issue it: 15 fountain pairs moved 2-5 steps; portal 5 and 13 removed (was (32, 2) <-> (18, 10)). |
| `weakhold_var1_gaps_doors` | 40x15 | xy | weakhold as the organisers might re-issue it: 1-250 beds become 1-200; 4 kelp edges opened (and their mirrors), e.g. at (34, 9). |
| `stripes_var1_portalsdel_fountains` | 24x12 | xy | Stripes as the organisers might re-issue it: portal 4 and 5 removed (was (2, 5) <-> (20, 7)); 6 fountain pairs moved 2-5 steps. |
| `tower_defense_var1_fountains_kelp` | 32x16 | xy | Tower Defense as the organisers might re-issue it: 2 fountain pairs moved 2-5 steps; 3 short kelp walls added (and their mirrors). |
| `islands_var1_thin_portalsdel` | 56x40 | y | Islands as the organisers might re-issue it: 80 of the 244 1-2559 beds silenced; portal 0 and 1 removed (was (10, 11) <-> (24, 16)). |
| `colosseum_var1_resym` | 16x16 | y | Colosseum as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. **SIDE(A)** |
| `arena_var1_resym` | 11x11 | y | Arena as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. |
| `autarky_var1_resym` | 54x18 | y | Autarky as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. |
| `devil_var1_resym` | 32x16 | xy | Devil as the organisers might re-issue it: SYMMETRY y becomes xy: team B's half is now team A's rotated. |
| `dilemma_var1_resym` | 32x16 | y | Prisoners Dilemma as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. **SIDE(A)** |
| `maze_var1_resym` | 48x24 | y | Maze as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right; 4 beds cut off where the halves meet were silenced. **SIDE(A)** |
| `portals_var1_resym` | 32x16 | y | Portals as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. |
| `queen_of_spades_var1_resym` | 25x35 | x | Queen Of Spades as the organisers might re-issue it: SYMMETRY xy becomes x: team B's half is now team A's mirrored top-bottom. |
| `schooltime_var1_resym` | 60x40 | xy | Schooltime as the organisers might re-issue it: SYMMETRY y becomes xy: team B's half is now team A's rotated. |
| `stripes_var1_resym` | 24x12 | y | Stripes as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right; 4 beds cut off where the halves meet were silenced. |
| `stronghold_var1_resym` | 48x24 | y | Stronghold as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right. |
| `tower_defense_var1_resym` | 32x16 | y | Tower Defense as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right; 8 beds cut off where the halves meet were silenced. |
| `trauma_var1_resym` | 48x24 | y | Trauma as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right; 8 beds cut off where the halves meet were silenced. |
| `trophy_var1_resym` | 25x25 | xy | Trophy as the organisers might re-issue it: SYMMETRY y becomes xy: team B's half is now team A's rotated. |
| `weakhold_var1_resym` | 40x15 | y | weakhold as the organisers might re-issue it: SYMMETRY xy becomes y: team B's half is now team A's mirrored left-right; 20 beds cut off where the halves meet were silenced. **SIDE(B)** |
| `australia_var1_gaps_kelp` | 64x64 | xy | Australia as the organisers might re-issue it: 8-30 beds become 4-15; 2 short kelp walls added (and their mirrors). |
| `unsw_var1_fountains_queen` | 64x64 | xy | Around UNSW as the organisers might re-issue it: 12 fountain pairs moved 2-5 steps; starter 2 (length 4) is now the queen instead of the length-4 one. |
| `big_empty_var1_fountains_kelp` | 64x64 | xy | Big Empty as the organisers might re-issue it: fountains added at (3, 35) and (16, 41) (and their mirrors); 2 short kelp walls added (and their mirrors). **SIDE(B)** |
| `colosseum_var1_queen_gaps` | 16x16 | xy | Colosseum as the organisers might re-issue it: the lone queen now faces the other way; 1-100 beds become 1-200; 1-250 beds become 1-500. |
| `arena_var1_kelp_fountains` | 11x11 | xy | Arena as the organisers might re-issue it: 3 short kelp walls added (and their mirrors); fountains added at (7, 9) and (2, 3) (and their mirrors). |
| `default_small_var1_portalsadd_gaps` | 16x16 | xy | Default Small as the organisers might re-issue it: portal added between (8, 8) and (14, 2) (and its mirror); 1-1000 beds become 1-500; 1-50 beds become 1-100. |
| `stronghold_var1_doors_gaps` | 48x24 | xy | Stronghold as the organisers might re-issue it: 4 kelp edges opened (and their mirrors), e.g. at (33, 14); 1-200 beds become 1-250. |
| `islands_var1_queen_gaps` | 56x40 | y | Islands as the organisers might re-issue it: starter 2 (length 3) is now the queen instead of the length-3 one; 1-200 beds become 1-100; 1-2559 beds become 1-1000. |

## behaviour suite (this folder)

| Map | Size | Sym | What this one adds |
|---|---|---|---|
| `open_16x16` | 16x16 | xy | Economy with nowhere to hide on a small wrap map: contact inside ten rounds, no walls to path around. **SIDE(B)** |
| `open_32x32` | 32x32 | xy | Pure economy and exploration: an open wrap field with thin beds; whoever spreads and splits better wins. |
| `open_64x64` | 64x64 | xy | Exploration at the size limit (Big Empty style): 4,096 tiles, homes at the quarter points about 60 steps apart, memory and turn time under load. |
| `centre_32x16` | 32x16 | xy | Opening race: all the food sits in a kelp ring both teams reach on the same round; homes are nearly empty. |
| `centre_y_25x25` | 25x25 | y | Opening race on a left/right mirror with an odd width: one shared axis column between two columns of fountains. |
| `homes_40x18` | 40x18 | xy | Punishes over-rushing: rich rooms behind 1-wide doors next to each start, a near-empty middle with a screen. |
| `portals_32x16` | 32x16 | xy | Route knowledge: rich 2x2 rooms entered only by portal, a fast lane to the middle, a tunnel into the enemy half. |
| `portals_y_48x24` | 48x24 | y | The same portal network on a bigger left/right mirror: more rooms, longer blind jumps. |
| `maze_48x24` | 48x24 | xy | Pocket mining and trap checks: 2-wide maze, fountains in dead ends behind 1-wide mouths, homes at both ends. |
| `maze_tight_32x16` | 32x16 | xy | Worst case for long bodies: a true 1-wide maze with fountains on dead-end tiles (kelp denser than any official map). |
| `lattice_32x16` | 32x16 | y | Head-on deadlocks: a grid of 1-wide corridors round sealed blocks, fountains at the crossings. |
| `lanes_32x16` | 32x16 | y | Devil-style lanes: long 1-wide lanes with only a few cross corridors, so a blocked lane is a long way round. **SIDE(A)** |
| `doomed_deadend_32x16` | 32x16 | xy | Queenless round 500 and reverse split: the L3 queen faces a dead end and is lost; an L11 can only be saved by a reverse split. |
| `doomed_coil_40x20` | 40x20 | xy | Coiled queen (Slithery Fight style): an L25 queen wound round her own head must shed her tail from the right segment. |
| `doomed_box_40x20` | 40x20 | xy | Boxed queen (current Schooltime style): an L4 queen fills a sealed 2x2 box; split, let the child die, then circle as L3. |
| `adjacent_24x24` | 24x24 | xy | Queen safety on round 0: the queens' heads are diagonal neighbours, so one tile is next to both on the first move. |
| `adjacent_y_25x16` | 25x16 | y | Queen safety on round 0, head on: the queens face each other with one shared tile between them. |
| `far_56x24` | 56x24 | xy | Feeding race: queens start in far-apart keeps with one door and food inside, 60+ steps apart. |
| `border_walled_40x20` | 40x20 | xy | Kelp-walled border (pair with border_wrap_40x20): edges are dead ends, the far side is far. |
| `border_wrap_40x20` | 40x20 | xy | Open wrap border (same layout as border_walled_40x20): the enemy is also behind you and distances halve. |
| `area_1089_33x33` | 33x33 | xy | 1,089 tiles, just under 1,100: the first of three maps for a bot whose play depends on map size. Compare with the next two. |
| `area_1100_55x20` | 55x20 | xy | Exactly 1,100 tiles, in a long 55x20 shape: the boundary case for a rule written as an area threshold. **SIDE(A)** |
| `area_1122_34x33` | 34x33 | xy | 1,122 tiles, just over 1,100, on a map of nearly the same shape as area_1089_33x33. |
| `symx_rooms_24x36` | 24x36 | x | SYMMETRY x (top/bottom mirror, unused by official maps): the enemy is above or below, not left or right. |
| `symx_centre_16x32` | 16x32 | x | SYMMETRY x on a tall map: the contested ring is reached by moving along y. |
| `tiny_10x10` | 10x10 | xy | Smallest legal size: the enemy is in view from the first turn; no time to build an economy. |
| `tiny_11x11` | 11x11 | xy | Tiny wrap map with an odd size (a centre tile): every direction leads to the enemy within 5 steps. |
| `tiny_12x12` | 12x12 | y | Tiny left/right mirror with two starters each: instant contact plus a first split decision. |
| `swarm7_48x24` | 48x24 | xy | Seven mixed-length starters per team (L7,4,10,2,5,2,2): early traffic at home, length-2 dragons that cannot split. **SIDE(A)** |
| `solo_24x24` | 24x24 | xy | A single L4 starter each (Colosseum style): the queen is the whole team until the first split. |
| `fountains_40x20` | 40x20 | xy | Fountain-heavy: 40+ spawn attempts a round, so both teams hit the 64-dragon cap early and must manage it. **SIDE(A)** |
| `barren_32x32` | 32x32 | xy | Barren: about 1.5 spawn attempts a round; every pearl is contested and splitting too early starves the team. |
| `decoys_40x20` | 40x20 | xy | Decoy pearls (as in Queen of Spades and Portals): rich beds sealed inside kelp boxes, visible but unreachable. |
| `unitlimit16_32x16` | 32x16 | xy | UNIT_LIMIT 16 (the engine supports the line; no official map sets it): a SPLIT past the limit is an illegal action and kills the dragon. |
