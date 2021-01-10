# Midterm Project: A Collection of Chinese and German Lullabies
Jocelyn Kavanagh and Rose Sun

## Summary
In this project, we developed a corpus of symbolic data representing 12 Chinese and 12 German lullabies divided into musical phrases for the analysis of musicology features that have cross-culturally soothing effects. We transcribed the lullabies from their original sources into .krn files using the Humdrum Toolkit. We define lullabies as children’s songs sung for soothing or sleep, and phrases as musical section marked by breath points. We solidified these definitions by selecting songs that were previously labeled as lullabies or that were a part of lullaby collections, and by listening to their audio recordings. The lullabies fell under the categories of German and Chinese depending on the language of the song or on the composer’s nationality (if available).

Together, Rose and Jocelyn, compiled the lullaby titles from the Mama Lisa website and the album “Chinese Folksong - Chinese Lullabies”. Rose was responsible for locating the Chinese lullabies in jianpu notation and transcribing them into Humdrum. Jocelyn was responsible for locating or synthezing symbolic reprentations for the German lullabies and transcribing them into Humdrum.

## Sampling Procedure
Initially, we looked to compile or extend existing folksong datasets from sources such as The Global Jukebox and The Essen Folk Song Collection. However, we learned that the content was limited or inaccessible for lullaby folk songs specifically. We then moved to look at child care websites with lists of nursery rhymes and lullabies. The most prolific source of information was the Mama Lisa website. The Mama Lisa site included lists of lyrics, videos, audio clips, and symbolic data for children’s songs and nursery rhymes from around the world. We used all of the available German and Chinese lullabies on Mama Lisa, yielding 12 German songs and 4 Chinese songs. To ensure group representation, we randomly sampled 8 songs from “Chinese Folksong - Chinese Lullabies”, an album of Chinese lullabies. After we created this list of 24 songs, we cross referenced their labels of lullaby and country of origin with sources such as Lieder-Archiv.de, Jianpuw.com, and Wikipedia.  

Once we created a list of 24 lullaby titles with their country of origin, we moved to synthesize the symbolic data. For the German lullabies, we used the available representations from Mama Lisa such as MIDI files and JPGs of score notation. Unfortunately, even though Mama Lisa provides the lyrics for every song, some songs are missing musical information. Additionally, some of the MIDI file content was inaccurate, therefore useless. In this case, we manually transcribed the lullabies from audio references either from the Mama Lisa page or from the first result with matching lyrics on YouTube from a reputable source (e.g., a German childcare content provider like “Kinderlieder zum Mitsingen und Bewegen”). For the Chinese lullabies, we found the JPGs of scores in their original jianpu notation from the Jianpu Website, and trans-notated them into staff notation. 


## Annotations
We then manually transcribed the scores into machine readable format using the Humdrum Toolkit. This allowed us to annotate phrase boundaries using standard Humdrum conventions. We defined a phrase as a musical section marked by breath points. To find the breath points, we listened to the audio recordings we previously referenced. Often, phrase boundaries aligned with rests. We did not include rests at the end of phrase boundaries as a part of the phrase. The humdrum representation includes only the sung melody of each lullaby. The lullabies often repeat melodic material for each stanza or refrain with different lyrics. We only transcribed one unique melodic refrain and did not note the number of repetitions, as this often varies. Each .krn file includes a melody spine, phrase boundaries, the composer (if available), the title in the original language, and the title in English. 

## Content 

Title | Country | Phrase Count | Measure Count
---- | ---- | ---- | ---- |
东北摇篮曲 (Northeastern Lullaby)| CHN | 10 | 17
槟榔树下摇网床 (Under the Areca Palm)| CHN | 12 | 16
星光摇篮曲 (Starlight Lullaby) | CHN | 10 | 22
侗乡摇篮曲 (Gaemi Lullaby) | CHN | 10 | 38
小银船 (Little Silver Boat) | CHN | 4 | 16
世上只有妈妈好 (Mom is the Best In the World) | CHN | 4 | 8
摇呀摇 (Yao Yah Yao) | CHN | 4 | 8
土家族摇篮曲 (Tujia Lullaby) | CHN | 4 | 8
月光光 (Moonlight) | CHN | 8 | 16
宝宝睡得甜 (Baby Sweet Dreams) | CHN | 4 | 12
黎族摇篮曲(Hlai Lullaby) | CHN | 6 | 16
睡吧, 小宝贝(Sleep, Baby) | CHN | 6 | 15
Abends Will Ich Schlafen Gehen (In the Evening, I Want To Go To Sleep) | DE | 10 | 20
Der Mond ist aufgegangen (The evening song) | DE | 6 | 12
Der Sandmann ist da (The Sandman is here) | DE | 5 | 9
Guten Abend, gute Nacht (Good Evening, Good Night) | DE | 8 | 16
Guten Mond, du gehst so stille (Dear Moon, you go so quietly) | DE | 8 | 16
Häschen in der Grube (Little Rabbit in your Burrow) | DE | 7 | 14
La-le-lu | DE | 16 | 30
Müde bin ich, geh zur Ruh (I’m Tired, I’m Going to Rest) | DE | 4 | 8
Schlaf, Kindlein, schlaf (Sleep Baby Sleep) | DE | 5 | 12
Schlafe, schlafe, holder, süßer Knabe (Sleep, Sleep, Fine, Sweet Boy) | DE | 8 | 8
Weißt du, wieviel Sternlein stehen (Do you know how many little stars there are?) | DE | 8 | 16
Wer hat die schönsten Schäfchen (Who has the most beautiful little sheep?) | DE | 4 | 7

## Descriptive Statistics

--- | Chinese | German | Total | 
--- | --- | --- | --- |
Number of .krn files | 12 | 12 | 24
Number of .mid files | 0 | 8 | 8
Mean Phrase Count | 6.83 | 7.42 | 7.26
Range Phrase Count | 8 | 12 | 12
Mean Length | 16 | 14 | 15
Range Length | 30 | 21 | 31
