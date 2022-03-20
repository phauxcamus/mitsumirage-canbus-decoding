Below is a list of all the node addresses seen.  Larger/complex nodes are split off into their own files.

Status Legend:
```
🟥 Seen (No further action)
🟨 Sample data gathered
🟩 Some data is decoded and understood
🟦 Decent understanding of how this node reports ("complete")
```

# Index
|Node|Status|Name|Category|
|:-|:-:|:-|:-:|
|[008](#008)|🟨|||
|[012](#012)|🟨|||
|[017](#017)|🟨|||
|[101](#101-engine-state)|🟩|Engine State|Engine|
|[1D0](#1D0)|🟨|||
|325|🟥|||
|328|🟥|||
|330|🟥|||
|338|🟥|||
|343|🟥|||
|347|🟥|||
|349|🟥|||
|356|🟥|||
|365|🟥|||
|390|🟥|||
|32B|🟥|||
|3AC|🟥|||
|415|🟥|||
|418|🟥|||
|[424](#424)|🟨|||
|[425](#425-external-access-state)|🟩|External Access State|Body|
|450|🟥|||
|[451](#451)|🟨|||
|453|🟥|||
|454|🟥|||
|4A0|🟥|||
|520|🟥|||
|5FE|🟥|||
|608|🟥|||
|6F0|🟥|||
|6FA|🟥|||
|6FB|🟥|||
|6FD|🟥|||
|6FF|🟥|||
|7BC|🟥|||

# Nodes

## `008`
### Observations
- Slow (1pps)

### Data
#### Data 1 (8 Bytes)
Constant `00 00 40 00 00 40 00 00`

## `012`
### Observations
- Slow (1pps)

### Data
#### Data 1 (6 Bytes)
Constant `00 00 00 00 00 00`

## `017`
### Observations
- Slow (1pps)

### Data
#### Data 1 (4 Bytes)
Constant 20 00 08 01

## `101` Engine State
### Observations
- Slow (1pps)
- Only seen while the vehicle is in any state but Key Off

### Data
#### Data 1 (1 Byte)
Known States:
- `01`: Briefly shows up when FAST button pressed
- `04`: Key on, engine off
- `44`: Engine cranking
- `84`: Engine running

## `1D0`
### Observations
- The three packets of data repeat constantly all the time and are always in the same order
- May be related to ETACS as it gets triggered by a bunch of different actions
- Doesn't react to any stimuli

### Data
#### Data 1 (8 Bytes)
Constant `02 51 06 53 00 5E 06 00`

#### Data 2 (8 Bytes)
Constant `02 1F 1E 60 0E 64 0E 00`

#### Data 2 (8 Bytes)
Constant `02 6F 0E 7B 06 00 00 00`


## `424`
### Observations
- Doesn't seem to react to any stimuli

### Data
#### Data 1 (8 Bytes)
Byte 6 constantly creeping up. Some kind of counter, minute resolution?

Samples:
- `08 00 00 01 1C 90 00 00`
- `98 00 04 01 26 F6 00 00`

## `425` External Access State
### Data
#### Data 1 (8 Bytes)
Bytes:
1. Constant `00`
2. Door State
	- `00`: All closed
	- `01`: Front Right
	- `03`: Front Left
3. Lock State
	- `01`: Locked
	- `02`: Unlocked
4. Constant `00`
5. Constant `00`
6. Constant `00`
7. Constant `00`
8. Constant `00`

### Notes
Door and Lock states are not fully mapped yet

## `451`
### Observations
- Doesn't react to any stimuli

### Data
#### Data 1 (8 Bytes)
Bytes:
1. Constant `FD`
2. Shifts from `31` to `13`
3. Constant `3F`
4. Constant `FF`
5. Constant `FF`
6. Constant `FF`
7. Constant `FF`
8. Constant `FF`