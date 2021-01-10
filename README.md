# A Comparison Between Chinese and German Lullabies
Jocelyn Kavanagh and Rose Sun

## Summary
In this project, we developed a corpus of symbolic data representing 12 Chinese and 12 German lullabies divided into musical phrases for the analysis of musicology features that have cross-culturally soothing effects. We transcribed the lullabies from their original sources into .krn files using the Humdrum Toolkit. We define lullabies as children’s songs sung for soothing or sleep, and phrases as musical section marked by breath points. We solidified these definitions by selecting songs that were previously labeled as lullabies or that were a part of lullaby collections, and by listening to their audio recordings. The lullabies fell under the categories of German and Chinese depending on the language of the song or on the composer’s nationality (if available).

Together, Rose and Jocelyn, compiled the lullaby titles from the Mama Lisa website and the album “Chinese Folksong - Chinese Lullabies”. Rose was responsible for locating the Chinese lullabies in jianpu notation and transcribing them into Humdrum. Jocelyn was responsible for locating or synthezing symbolic reprentations for the German lullabies and transcribing them into Humdrum.

We then tested our hypothesis that lullabies have cross-culturally soothing effects. We focused on soothing effects due to melodic structure. We constrained melodic structure as the ratio of steps and leaps in a song, the note density of a song, the ratio of long and short notes in a song, the phrase lengths found in a song, and the contour of phrases found in a song. We analyzed these features using Music21 and Humdrum, then we ran statistical tests to find similarity. We ran individual T-tests and a Chi-Square test, and we failed to find a significant difference between Chinese and German lullabies across all our melodic features, as predicted. 

## File Guide
Corpus folder includes the krn files that we transcribed and compiled. The corpus description pdf describes the contents of the corpus and our procedures for creating it. The final project Jupyter Notebook includes the code we wrote to analyze our corpus and run our statistics. The final paper pdf describes our analysis process and its outcomes.

## Corpus Details

### Sampling Procedure
Initially, we looked to compile or extend existing folksong datasets from sources such as The Global Jukebox and The Essen Folk Song Collection. However, we learned that the content was limited or inaccessible for lullaby folk songs specifically. We then moved to look at child care websites with lists of nursery rhymes and lullabies. The most prolific source of information was the Mama Lisa website. The Mama Lisa site included lists of lyrics, videos, audio clips, and symbolic data for children’s songs and nursery rhymes from around the world. We used all of the available German and Chinese lullabies on Mama Lisa, yielding 12 German songs and 4 Chinese songs. To ensure group representation, we randomly sampled 8 songs from “Chinese Folksong - Chinese Lullabies”, an album of Chinese lullabies. After we created this list of 24 songs, we cross referenced their labels of lullaby and country of origin with sources such as Lieder-Archiv.de, Jianpuw.com, and Wikipedia.  

Once we created a list of 24 lullaby titles with their country of origin, we moved to synthesize the symbolic data. For the German lullabies, we used the available representations from Mama Lisa such as MIDI files and JPGs of score notation. Unfortunately, even though Mama Lisa provides the lyrics for every song, some songs are missing musical information. Additionally, some of the MIDI file content was inaccurate, therefore useless. In this case, we manually transcribed the lullabies from audio references either from the Mama Lisa page or from the first result with matching lyrics on YouTube from a reputable source (e.g., a German childcare content provider like “Kinderlieder zum Mitsingen und Bewegen”). For the Chinese lullabies, we found the JPGs of scores in their original jianpu notation from the Jianpu Website, and trans-notated them into staff notation. 


### Annotations
We then manually transcribed the scores into machine readable format using the Humdrum Toolkit. This allowed us to annotate phrase boundaries using standard Humdrum conventions. We defined a phrase as a musical section marked by breath points. To find the breath points, we listened to the audio recordings we previously referenced. Often, phrase boundaries aligned with rests. We did not include rests at the end of phrase boundaries as a part of the phrase. The humdrum representation includes only the sung melody of each lullaby. The lullabies often repeat melodic material for each stanza or refrain with different lyrics. We only transcribed one unique melodic refrain and did not note the number of repetitions, as this often varies. Each .krn file includes a melody spine, phrase boundaries, the composer (if available), the title in the original language, and the title in English. 

## Analysis Details

### Melodic Structure Definitions
#### Step to Leap Ratio
Supporting the hypothesis that lullabies would have more stepwise motion than leapwise motion, we investigated the ratio of steps and leaps in each song. We defined a step as melodic movement up or down by 1-3 semitones, and we defined a leap as any movement greater. We chose to include minor thirds (3 semitones) as steps due to the pentatonic nature of some of the Chinese songs in the corpus.
To find the step to leap ratio for each song, we used the Music21 interval object to extract the melodic intervals for each song. Then, we iteratively counted the number of step and leap intervals according to our operational definition. A ratio was assigned to each song by dividing the number of steps by the number of leaps.
#### Note Density
We hypothesized that lullabies would be slower to induce more soothing qualities, however, our manually transcribed corpus lacked accurate tempi information. As such, we decided to evaluate the temporal complexity by finding the note density. The note density is defined as the average number of notes per measure for each song. In this definition, rests are not counted as notes, and ties are counted as one note.
We found the note density for each song by finding the number of notes and the number of measures in the song through the Music21 note and parts object. We then divided the number of notes by the number of measures for the note density.
#### Long to Short Note Duration Ratio
Again, due to our interest in the pace of the lullabies but without accurate tempo information, we used note duration and the ratio between long and short notes as another marker for temporal complexity. The definition of long and short notes depends on the given songs meter because it relies on the number of beats per measure. We defined the long notes of a song as any note with a beat value of greater than or equal to half of the beats per measure. For example, in 4/4 a long note is a half note (2 beats) or greater.
We found the long to short note ratios with the Music21 getTimeSignatures function and by recursing through the Music21 Note objects in a song. We calculated the center number of beats by dividing the numerator of the time signature by two. Then, following our operational definition, we iteratively counted the number of long and short notes in the song by comparing the note duration quarter length values to the measure center. The ratio for each song was calculated by dividing the number of long notes by the number of short notes.
#### Phrase Length
To investigate the structural similarities of the Chinese and German songs, we extracted the length of each phrase in each song. Phrase length is defined as the number of notes in between two breath points, where rests do not count as notes. Phrase length was calculated by extracting and iterating through each song’s Humdrum spine. The beginning and end of phrases were marked by “{“ and “}” in the .krn files.
#### Contour
Contour was the most difficult melodic feature to define. We deliberated between using intervallic distances or maximum and minimum note placements. Ultimately, we defined contour as the shape of a phrase as determined by the position of the highest and lowest note in the phrase, along with the pitch of the first and last note of the phrase. We developed 7 different contour categories: flat, ascending (“/”), descending (“\”), V-shaped (“V”), arch (“/\”), N-shaped (“N”), and reverse N (“\/\”).
To collect the contour types, we extracted the Humdrum spines with the notes listed as their frequency values, and we iterated through the phrases. Following the logic outlined below, we categorized each phrase as a contour type. For the contour assignment algorithm, a midpoint frequency was calculated for each phrase by finding the average between the highest and lowest frequency. <br>
##### Flat: 
The frequencies of the highest and lowest notes are equal. <br>
##### Ascending: <br>
- The lowest note is the first note and the highest note is the last note
- The first note’s frequency is lower than the midpoint frequency, the lowest note appears before the highest note, and the last note is higher than the midpoint <br>
##### Descending: <br>
- The highest note is the first note and the lowest note is the last note
- The first note’s frequency is higher than the midpoint frequency, the highest note appears before the lowest note, and the last note is lower than the midpoint <br>
##### V-Shaped: 
The first and last note is higher than the midpoint frequency, so the lowest note is somewhere in the middle. <br>
##### Arch: 
The first and last note is lower than the midpoint frequency, so thehighest note is somewhere in the middle. <br>
##### N-Shaped: 
Multiple non-consecutive lowest and highest notes are found in the phrase, the first note’s frequency is lower than the midpoint, and the last note’s frequency is higher than the midpoint <br>
##### Reverse N: 
Multiple non-consecutive lowest and highest notes are found in the phrase, the first note’s frequency is higher than the midpoint, and the last note’s frequency is lower than the midpoint <br>
