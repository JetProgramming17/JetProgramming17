package com.company;

public class Main {

    public static void main(String[] args) {
        //one dimensional array declaring the three months
        String[] months = {"JAN", "FEB","MAR"};
        //one dimensional array declaring the cities
        String[] cities ={"JHB","DBN","CTN","PE"};
   // A two dimensional array of speeds from january to march for four cities
        int[][] speeds = {
                {128,135,139},
                {155,129,175},
                {129,130,185},
                {195,155,221}
        };
        //loop through the array to get the first highest speeds fines
        int first_highest = 0;
        int first_highest_row = 0;
        int first_highest_column = 0;

        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
               if(speeds[i][j] > first_highest)
               {
                   first_highest = speeds[i][j];
                   first_highest_row = i;
                   first_highest_column = j;
               }

            }
        }
        //loop through the array to get the second highest speeds fines
        int second_highest = 0;
        int second_highest_row = 0;
        int second_highest_column = 0;
        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
                if(speeds[i][j] > second_highest && speeds[i][j] != first_highest  )
                {
                    second_highest = speeds[i][j];
                    second_highest_row = i;
                    second_highest_column = j;
                }

            }
        }
        //loop through the array to get the third highest speeds fines
        int third_highest = 0;
        int third_highest_row = 0;
        int third_highest_column = 0;
        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
                if( speeds[i][j] > third_highest && speeds[i][j] < first_highest && speeds[i][j] < second_highest  )
                {
                    third_highest = speeds[i][j];
                    third_highest_row = i;
                    third_highest_column = j;
                }
            }
        }

        //Lopp through to find the first lowest
        int first_lowest = 2000;
        int first_lowest_row = 0;
        int first_lowest_column = 0;

        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
                if(speeds[i][j] < first_lowest)
                {
                    first_lowest = speeds[i][j];
                    first_lowest_row = i;
                    first_lowest_column = j;
                }

            }
        }
        //Lopp through to find the second lowest
        int second_lowest = 2000;
        int second_lowest_row = 0;
        int second_lowest_column = 0;
        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
                if(speeds[i][j] < second_lowest && speeds[i][j] != first_lowest )
                {
                    second_lowest = speeds[i][j];
                    second_lowest_row = i;
                    second_lowest_column = j;
                }
            }
        }

        //Lopp through to find the third lowest
        int third_lowest = 2000;
        int third_lowest_row = 0;
        int third_lowest_column = 0;
        for(int i = 0; i<speeds.length; i++)
        {
            for(int j = 0; j<speeds[i].length; j++)
            {
                if( speeds[i][j] < third_lowest && speeds[i][j] != first_lowest && speeds[i][j] != second_lowest)
                {
                    third_lowest = speeds[i][j];
                    third_lowest_row = i;
                    third_lowest_column = j;
                }
            }
        }
        System.out.println("\nA REPORT FOR MONTHLY SPEEDINGS FINES RECORDED FOR FOUR CITIES WITHIN THREE MONTHS.\n");
        System.out.println("The three highest speeding fines in the four cities for the three moths are: ");
        System.out.println("fist Highest is "+first_highest +"Km on "+months[first_highest_column]+" from "
        +cities[first_highest_row] +" city");
        System.out.println("second highest is "+second_highest+"Km on "+months[second_highest_column]+" from "
                +cities[second_highest_row] +" city");
        System.out.println("third highest is "+third_highest+"Km on "+months[third_highest_column]+" from "
                +cities[third_highest_row] +" city");

        //printint the lowest speed fines
        System.out.println("\nThe three Lowest speeding fines in the four cities for the three moths are: ");
        System.out.println("fist Lowest is "+first_lowest +"Km on "+months[first_lowest_column]+" from "
                +cities[first_lowest_row] +" city");
        System.out.println("second Lowest is "+second_lowest+"Km on "+months[second_lowest_column]+" from "
                +cities[second_lowest_row] +" city");
        System.out.println("third Lowest is "+third_lowest+"Km on "+months[third_lowest_column]+" from "
                +cities[third_lowest_row] +" city");

    }
}
