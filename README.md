Initial project works on the principle of "Total Bases Created" for doing projections.

The Master Data is created by pulling from the Lahman Data and filtering for players with 0 PA per season. From that filtered data we create Adjsuted Net Bases Created for each pl;ayer per season like so"

Total Bases Created (TBC) is conceptually the number of bases a player contributes. TBC is computed thus:
  TB + BB + SB + SH + RBI + HBP

This gets combined with the Total Outs Created(TOC) by the player which is computed thus:
  PA - H - BB + GIDP + CS + SF

The TOC is multiplied by (League TBC/League TOC) factor to convert the outs created into bases created

This number (TBC - (TOC * (League TBC/League TOC) represents the unadjusted Net Bases Created (NBC) for the player for that team that season

Unadjusted NBC is scaled by an age factor and park factor for the player for that team that season

Players are then consolidated to a single Adjusted NBC per season so each player has a single Adjusted NBC per season

These player computations are then consolidated into a data frame of all the players in the targeted time frame with greater than 0 PA for each of the seasons used for projection
