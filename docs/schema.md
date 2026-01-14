# Processed Dataset Schema

This schema documents key fields in the processed Spotify listening dataset used for analysis and visualisation. It consists of fields that are part of the raw data and fields derived from the raw data. It is not an exhaustive description of all intermediate or raw fields.

## Fields

### Original Fields

#### Track-Level Information Fields

- `master_metadata_track_name` (*string*)
    This field is the name of the track.

- `master_metadata_album_artist_name` (*string*)
    This field is the name of the artist, band or podcast.

- `master_metadata_album_album_name` (*string*)
    This field is the name of the album of the track.

- `spotify_track_uri` (*string*)
    A Spotify URI, uniquely identifying the track in the form of “spotify:track:<base-62string>”. A Spotify URI is a resource identifier that you can enter, for example, in the Spotify Desktop client’s search box to locate an artist, album, or track.

#### Date/Time Fields

All date and time fields are in UTC (Coordinated Universal Time).

- `ts` (*timestamp (UTC)*)
    This field is a timestamp indicating when the track stopped playing. The order is year, month and day followed by a timestamp in military time.

#### Playback & Behaviour Fields

- `ms_played` (*integer*)
    This field is the number of milliseconds the stream was played.

- `reason_start` (*string*)
    This field is a value telling why the track started (e.g. “trackdone”).

- `reason_end` (*string*)
    This field is a value telling why the track ended (e.g. “endplay”).

- `shuffle` (*boolean*)
    This field has the value True or False depending on if shuffle mode was used when playing the track.

- `skipped` (*boolean*)
    This field indicates if I skipped to the next song.

### Derived Fields

The following fields were calculated using the original fields that came with the raw data. They facilitate analysis and visualisations.

#### Date/Time Fields

All date and time fields are in UTC (Coordinated Universal Time).

- `date` (*date*)
    This field is a date indicating when the track stopped playing. The order is year, then month, then day.

- `year` (*integer*)
    This field is an integer denoting the year when the track stopped playing.

- `month` (*integer*)
    This field is an integer denoting the month when the track stopped playing.

- `year_month` (*month*)
    This field is a year and month indicating when the track stopped playing. The order is year, then month.

- `hour` (*integer*)
    This field is an integer denoting the hour when the track stopped playing.

- `day_of_week` (*integer*)
    This field is an integer that denotes the day number of the week, indicating when the track stopped playing. The week starts on Monday, which is denoted by 0 and ends on Sunday which is denoted by 6.

- `day_name` (*string*)
    This field is a day name indicating when the track stopped playing.

#### Playback & Behaviour Fields

- `listening_hours` (*float*)
    This field is the number of hours the stream was played. It is derived from the `ms_played` field.

- `track_play_count` (*integer*)
    This field is the integer, 1. It is used to help count plays.

- `skip_flag` (*integer*)
    This field is the integer 1 if I skipped to the next song, and the integer 0 if I didn't. It is derived from the `skipped` field.

- `completed_flag` (*integer*)
    This field is the integer 0 if I skipped to the next song, and the integer 1 if I didn't. It is derived from the `skipped` field.

- `valid_play` (*boolean*)
    This field indicates if a stream is a valid play, that is, if the stream played for more than 30,000 milliseconds (30 seconds). It is derived from the `ms_played` field.
