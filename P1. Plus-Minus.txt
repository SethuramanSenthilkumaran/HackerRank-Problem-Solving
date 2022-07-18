import java.io.*;
import java.math.*;
import java.security.*;
import java.text.*;
import java.util.*;
import java.util.concurrent.*;
import java.util.function.*;
import java.util.regex.*;
import java.util.stream.*;
import static java.util.stream.Collectors.joining;
import static java.util.stream.Collectors.toList;

class Result {

    /*
     * Complete the 'plusMinus' function below.
     *
     * The function accepts INTEGER_ARRAY arr as parameter.
     */

    public static void plusMinus(List<Integer> arr) {
    // Write your code here
        int count = arr.size(), z_count = 0, p_count = 0, n_count = 0;
        for(int a:arr){
            if(a < 0){
                n_count++;
            }
            else if(a == 0){
                z_count++;
            }
            else{
                p_count++;
            }
        }
        float p_ans = (float)p_count/count;
        float n_ans = (float)n_count/count;
        float z_ans = (float)z_count/count;
        System.out.println(String.format("%.6f", p_ans));
        System.out.println(String.format("%.6f", n_ans));
        System.out.println(String.format("%.6f", z_ans));
    }

}

public class Solution {
    public static void main(String[] args) throws IOException {
        BufferedReader bufferedReader = new BufferedReader(new InputStreamReader(System.in));

        int n = Integer.parseInt(bufferedReader.readLine().trim());

        List<Integer> arr = Stream.of(bufferedReader.readLine().replaceAll("\\s+$", "").split(" "))
            .map(Integer::parseInt)
            .collect(toList());

        Result.plusMinus(arr);

        bufferedReader.close();
    }
}
