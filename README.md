# NBA-Fatigue

Idea vommit:

- make a notebook(s) that gets the necessary data
- (maybe) store the data as tables in a database
- merge the data into a single file
- use old seasons to predict the most recent 2-3 seasons

Data:

- Games (home team, away team, date, time)
  - start time doesn't seem to be in the nba api. I might need to find a way to get that
  - or is it in the box score?
- location (coordinates of each arena, elevation of the city)
- for each team

  - games in the last n days (3, 5, 7)
  - home vs away for previous games (x out of y games are away. Or maybe have a column for each n previous game and if it was home vs away)
  - is it a flight or a drive (might have to just set a distance threshold for this)
  - days of rest, opponents days of rest

- physicality of the opponent (number of fouls committed in previous game compared to team average or league average)
- difference in teams skill (absolute value of the difference in standings, or difference in wins/losses)
- does either team have a playoff position locked (or on the line)

- Also worth taking some time to think about what data we include
  - Are we trying to predict the outcome of every game? Or are we specifically trying to hone in on scheduled losses

The Mah score seems to put things on a scale of 1-10 and then sets two thresholds for general alert vs red alert

- I could try to use score percentiles to make the scale of 1-10?
- If I can find Mah data for several seasons I could use the mah score as the target

What do I want the target of the model to be?

- binary, will the team win or lose
- regression, what will be the difference in score (team of interest - opponent, can be positive or negative)
- use the mah score as the target if I can find the data

What should the final dataframe looklike?

- It should include these columns
  - team of interest
  - opponent
  - home or away
  - num of days since last game
  - number of consecutive home games
  - number of consecutive away games
  - distance traveled to current game
  - distance traveled to current game (cumulative)
  - num of games in last 3 days
  - win or loss
  - score differential
  - number of turnovers (and how many this is above or below the teams average)
  - number of fouls (and how this compares against season or against rested games)
