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
|[152](#152)|🟨|||
|[154](#154)|🟨|||
|[185](#185-climate-control)|🟨|Climate Control|Infotainment|
|[186](#186-chimebeep)|🟨|Chime/Beep|Infotainment|
|[1B6](#1B6)|🟨|||
|[1C2](#1C2)|🟨|||
|[1D0](#1D0)|🟨|||
|[1D1](#1D1)|🟨|||
|[2D0](#2D0)|🟨|||
|[2F1](#2f1-steering-angle)|🟨|Steering Angle|Chassis|
|[200](#200)|🟨|||
|[208](#208)|🟨|||
|[210](#210)|🟨|||
|[212](#212)|🟨|||
|[214](#214)|🟨|||
|[215](#215)|🟨|||
|[218](#218)|🟨|||
|[236](#236-steering-adv)|🟨|Steering A/D/V|Chassis|
|[255](#255)|🟨|||
|[265](#265)|🟨|||
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

## `152`
### Observations
- Slow (1pps)

### Data
#### Data 1 (8 Bytes)
Bytes: `00 4C 01 71 00 00 00 00`
1. Constant ``
2. Shifts up and down between `4C` and `4E`
3. Constant `01`
4. Constant `71`
5. Constant `00`
6. Constant `00`
7. Constant `00`
8. Constant `00`

## `154`
### Data
#### Data 1 (8 Bytes)
Byte 1 shifts between 71 and 72

## `185` Climate Control?
### Data
#### Data 1 (8 Bytes)
Bytes: `03 00 00 00 01 00 00 00`
1. Various, but shifts up one point when the AC Clutch is on
2. Defrost Mode
    - `00`: Off
    - `01`: On
3. Constant `00`
4. Constant `00`
5. AC Compressor Enabled (Snowflake icon)
    - `00`: Off
    - `01`: On
6. Constant `00`
7. Constant `00`
8. Constant `00`


## `186` Chime/Beep?
### Data
#### Data 1 (8 Bytes)
Constant 8x `00`
Byte 6: Number of Beeps

## `1B6`
### Observations
- Slow (1pps)

### Data
#### Data 1 (8 Bytes)
Constant `00 01 00 00 00 00 00 00`

## `1C2`
### Observations
- Slow (1pps)

### Data
#### Data 1 (8 Bytes)
Constant `00 24 0D 00 00 00 00 00`

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

## `1D1`
### Observations
- Slow (2pps)

### Data
#### Data 1 (8 Bytes)
Constant `01 09 00 80 69 88 00 55`

## `2D0`
### Observations
- Slow (`pps)

### Data
#### Data 1 (8 Bytes)
Constant `40 00 00 00 00 00 00 00`

## `2F1` Steering Angle
### Data
#### Data 1 (8 Bytes)
Bytes: `00 00 14 CA 00 00 00 00`
- Last 4 bytes always 00

### Notes
See [236](#236-steering-adv) for cleaner output

## `200`
### Observations
- Data is reported constantly and in sequence
- No reaction

### Data
#### Data 1 (8 Bytes)
`00 22 00 00 C0 00 C0 00`

#### Data 2 (8 Bytes)
`00 22 00 00 00 00 00 00`

#### Data 3 (8 Bytes)
`00 E2 00 00 40 00 40 00`

#### Data 4 (8 Bytes)
`00 E2 00 00 80 00 80 00`

## `208`
### Observations
- Data is reported constantly and in sequence
- No reaction

### Data
#### Data 1 (8 Bytes)
`38 20 00 00 00 00 00 00`

#### Data 2 (8 Bytes)
`38 20 00 00 00 00 00 00`

#### Data 3 (8 Bytes)
`38 20 30 00 00 00 40 00`

#### Data 4 (8 Bytes)
`38 20 30 00 00 00 40 00`

## `210`
### Observations
- Commanded RPM?
- Data is reported constantly and in sequence

### Data
#### Data 1 (8 Bytes)
`00 00 00 00 40 00 00 FF`

#### Data 2 (8 Bytes)
`00 00 00 00 40 00 00 FF`

#### Data 3 (8 Bytes)
`00 00 00 80 C0 00 00 FF`

#### Data 4 (8 Bytes)
`00 00 00 80 C0 00 00 FF`

## `212`
### Observations
- Random Data?
- First 2 bytes `00`

## `214`
### Observations
- Data is reported constantly and in sequence
- No reaction
- First 6 bytes same as [215](#215)

### Data
#### Data 1 (8 Bytes)
`00 00 6D D9 6D F6 03 00`

#### Data 2 (8 Bytes)
`00 00 6D D9 6D F6 03 00`

#### Data 2 (8 Bytes)
`00 00 6D D9 6D F6 00 00`

#### Data 4 (8 Bytes)
`00 00 6D D9 6D F6 00 00`


## `215`
### Observations
- Data is reported constantly and in sequence
- No reaction
- First 6 bytes same as [214](#214)

### Data
#### Data 1 (8 Bytes)
`00 00 6D D9 6D F6 04 00`

#### Data 2 (8 Bytes)
`00 00 6D D9 6D F6 04 00`

#### Data 3 (8 Bytes)
`00 00 6D D9 6D F6 07 00`

#### Data 4 (8 Bytes)
`00 00 6D D9 6D F6 07 00`


## `218`
### Observations
- Data is reported constantly and in sequence
- No reaction

### Data
#### Data 1 (8 Bytes)
`CA A8 DD 40 00 88 FF 00`

#### Data 2 (8 Bytes)
`CA A8 DD 40 00 88 FF 00`

#### Data 3 (8 Bytes)
`4A A8 DD 40 00 08 FF 00`

#### Data 4 (8 Bytes)
`4A A8 DD 40 00 08 FF 00`

## `236` Steering A/D/V?
### Observations
- Bytes 6-7 always 00
- Less noisy than [2F1](#2f1-steering-angle)

## `255`
### Data
#### Data 1 (8 Bytes)
Constant `00 00 3F FF 3F FF FF FF`

## `265`
### Observations
- RPM, Load, Fuel?
- Increases with RPM


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