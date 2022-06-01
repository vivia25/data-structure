public class Song 
{

    private String songTitle;
    private String artist;
    private int lengthInSeconds;
/**
     * Constructor
     *
     * @param initialSongTitle value to store the song title. 
     * @param initialArtist value to store the name of artist.
     * @param initialLengthInSeconds value to store the length in seconds of
     * the song.
     */
     public Song(String initialSongTitle, String initialArtist, 
                int initialLengthInSeconds) 
    {
        this.songTitle = initialSongTitle;
        this.artist = initialArtist;
        this.lengthInSeconds = initialLengthInSeconds;

    }
/**
 * The getSongTitle method returns the song title.
 * @return the value in the songTitle field.
 */
    public String getSongTitle() {
        return this.songTitle;
    }
/**
 * The getArtist method returns the artist name.
 * @return the value in the getArtist field.
 */
    public String getArtist() {
        return this.artist;
    }
    /**
 * The getLengthInSeconds returns the length in seconds of the song.
 * @return the value in the getLengthInSeconds field.
 */
    public int getLengthInSeconds() {
        return this.lengthInSeconds;
    }
/**
 * The setSongTitle method stores a value in the newSongTile field.
 * @param newSongTitle The value to store in songTitle.
 */
    public void setSongTitle(String newSongTitle) {
        this.songTitle = newSongTitle;
    }
/**
 * The setArtist method stores a value in the initialArtist field.
 * @param initialArtist The value to store in initialArtist.
 */
    public void setArtist(String initialArtist) {
        this.artist = initialArtist;
    }
   

}
