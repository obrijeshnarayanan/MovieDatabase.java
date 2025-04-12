import java.util.Scanner;

class Movie {
    public String MovieTitle;
    public String Director;
    public String Producer;
    public int ReleasedYear;
    public int NoOfCharacters;

    public Movie(String MovieTitle, String Director, String Producer, int ReleasedYear, int NoOfCharacters) {
        this.MovieTitle = MovieTitle;
        this.Director = Director;
        this.Producer = Producer;
        this.ReleasedYear = ReleasedYear;
        this.NoOfCharacters = NoOfCharacters;
    }

    public void getMovie() {
        System.out.println("Movie Name: " + MovieTitle);
        System.out.println("Directed by: " + Director);
        System.out.println("Produced by: " + Producer);
        System.out.println("Year of Release: " + ReleasedYear);
    }
}

class Bollywood extends Movie {
    private String Language = "Hindi";

    public Bollywood(String MovieTitle, String Director, String Producer, int ReleasedYear, int NoOfCharacters) {
        super(MovieTitle, Director, Producer, ReleasedYear, NoOfCharacters);
    }

    public void getMovie() {
        super.getMovie();
        System.out.println("Language: " + Language);
    }
}

class Mollywood extends Movie {
    private String Language = "Malayalam";

    public Mollywood(String MovieTitle, String Director, String Producer, int ReleasedYear, int NoOfCharacters) {
        super(MovieTitle, Director, Producer, ReleasedYear, NoOfCharacters);
    }

    public void getMovie() {
        super.getMovie();
        System.out.println("Language: " + Language);
    }
}

public class MovieDatabase {
    public static void main(String[] args) {
        Scanner scan = new Scanner(System.in);

        int NoOfCharacters = 7;
        Mollywood malMovie = new Mollywood("Premalu", "Girish AD", "Fahadh Faasil", 2024, NoOfCharacters);
     // Arrays to store actors and characters
        String[] actors = new String[NoOfCharacters];
        String[] characters = new String[NoOfCharacters];

        // Collecting actor and character names
        for (int i = 0; i < NoOfCharacters; i++) {
            System.out.print("Enter Actor Name: ");
            actors[i] = scan.nextLine();
            System.out.print("Enter Character Name: ");
            characters[i] = scan.nextLine();
        }
        malMovie.getMovie();
        for (int i = 0; i < NoOfCharacters; i++) {
            System.out.println(actors[i] + " as " + characters[i]);
        }

        scan.close();
    }
}
