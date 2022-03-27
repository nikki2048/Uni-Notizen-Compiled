# Herzlich Willkommen im ersten Semester
Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet. Lorem ipsum dolor sit amet, consetetur sadipscing elitr, sed diam nonumy eirmod tempor invidunt ut labore et dolore magna aliquyam erat, sed diam voluptua. At vero eos et accusam et justo duo dolores et ea rebum. Stet clita kasd gubergren, no sea takimata sanctus est Lorem ipsum dolor sit amet.

```java
import java.util.Scanner;

public class Life {
    public static void show(boolean[][] grid){
        String s = "";
        for(boolean[] row : grid){
            for(boolean val : row)
                if(val)
                    s += "*";
                else
                    s += ".";
            s += "\n";
        }
        System.out.println(s);
    }
    
    public static boolean[][] gen(){
        boolean[][] grid = new boolean[10][10];
        for(int r = 0; r < 10; r++)
            for(int c = 0; c < 10; c++)
                if( Math.random() > 0.7 )
                    grid[r][c] = true;
        return grid;
    }
    
    public static void main(String[] args){
        boolean[][] world = gen();
        show(world);
        System.out.println();
        world = nextGen(world);
        show(world);
        Scanner s = new Scanner(System.in);
        while(s.nextLine().length() == 0){
            System.out.println();
            world = nextGen(world);
            show(world);
            
        }
    }
    
    public static boolean[][] nextGen(boolean[][] world){
        boolean[][] newWorld 
            = new boolean[world.length][world[0].length];
        int num;
        for(int r = 0; r < world.length; r++){
            for(int c = 0; c < world[0].length; c++){
                num = numNeighbors(world, r, c);
                if( occupiedNext(num, world[r][c]) )
                    newWorld[r][c] = true;
            }
        }
        return newWorld;
    }
    
    public static boolean occupiedNext(int numNeighbors, boolean occupied){
        if( occupied && (numNeighbors == 2 || numNeighbors == 3))
            return true;
        else if (!occupied && numNeighbors == 3)
            return true;
        else
            return false;
    }

    private static int numNeighbors(boolean[][] world, int row, int col) {
        int num = world[row][col] ? -1 : 0;
        for(int r = row - 1; r <= row + 1; r++)
            for(int c = col - 1; c <= col + 1; c++)
                if( inbounds(world, r, c) && world[r][c] )
                    num++;

        return num;
    }

    private static boolean inbounds(boolean[][] world, int r, int c) {
        return r >= 0 && r < world.length && c >= 0 &&
        c < world[0].length;
    }
}
```

![[root#welcome-to-dendron:#lookup]]

# Mathe
$\int\limits_{0}^{\infty} 3x^2 - 2x + 3 \:\: dx = \frac{3x^3}{3}-\frac{2x^2}{2}+\frac{3x}{1}$