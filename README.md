# Blog
import java.util.*;
public class Main {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int H = sc.nextInt();
        int W = sc.nextInt();
        String[][] arr = new String[H][W];
        int sx = -1;
        int sy = 0;
        for(int y = 0;y < H;y++){
            String line = sc.next();
            int ssx = line.indexOf("S");
            arr[y] = line.split("");
            if(ssx != -1){
                sy = y;
                sx = ssx;
            }
        }
        try {
            for(;;){
                if(".".equals(arr[sy + 1][sx])){
                    sy++;
                    if(sy >= H){
                        System.out.println("YES");
                        return;
                    }
                    arr[sy][sx] = "S";
    
                }else
                if(".".equals(arr[sy - 1][sx])){
                    sy--;
                    if(sy < 0){
                        System.out.println("YES");
                        return;
                    }
                    arr[sy][sx] = "S";
    
                }else
                
                if(".".equals(arr[sy][sx - 1])){
                    sx--;
                    if(sx < 0){
                        System.out.println("YES");
                        return;
                    }
                    arr[sy][sx] = "S";
                }else
                if(".".equals(arr[sy][sx + 1])){
                    sx++;
                    if(sx >= W){
                        System.out.println("YES");
                    }
                    arr[sy][sx] = "S";
                }else{
                    System.out.println("NO");
                    return;
                }
            }
        } catch(Exception e) {
            System.out.println("YES");
        }
        
    }
}
