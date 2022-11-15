
# SPWN-MIDI

A simple library that allows you to parse MIDI files. (It might be buggy, I didn't test it well lol).

Type 2 MIDI files and SysEx events are not supported.

# Usage

This library exports one function: parse. It takes one argument, that is an array of bytes in the MIDI file (readfile function can be used).

## Result

### MIDI

| Parameter | Type | Description |  
| :-------- | :---- | :--------- |
| midi_type | Integer | Type of the MIDI file (0-1, 2 is not supported) |
| tracks | Array\<Track> | Array of all tracks in the sequence |
| time_division | Integer | Time division of the sequence |
| _raw | Object | Object containing header and array of tracks |

### Track

| Parameter | Type | Description |  
| :-------- | :---- | :--------- |
| chunk_size | Integer | Size of the track chunk in bytes |
| events | Array\<Object> | Array that contains all of the track's events |
| bpm | Number | Tracks finish tempo (last tempo set in the track, default 120) |

