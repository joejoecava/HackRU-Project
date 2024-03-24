public class FitnessCalculators {
    public static void main(String[] args) {
        System.out.println(" ");
        System.out.println ("Type ''Calorie'' for daily calorie calculator");
        System.out.println ("Type ''Max'' for 1 rep max (strength) calculator");
        System.out.println("Type ''Water'' for daily water/hydration calculator");
        System.out.println("Type ''Macronutrients'' for daily macronutrients calculator");
        System.out.println("Type ''Days'' for days until you reach your goal weight calculator");
        System.out.println("Type ''Burned'' for calories burned performing a certain exercise");
        String whichFunction = StdIn.readString();

        if (whichFunction.equals("Calorie")){
            System.out.println(" ");
            System.out.println("Enter: Gender (Male or Female)");
            String g = StdIn.readString();
            System.out.println("Enter: Height (inches)");
            int h = StdIn.readInt();
            System.out.println("Enter: Weight (lbs)");
            int w = StdIn.readInt();
            System.out.println("Enter: Age (years)");
            int a = StdIn.readInt();
            System.out.println("Enter: Days of Exercise Per Week (0-7)");
            int d = StdIn.readInt();
            System.out.println(" ");
            System.out.println("You Entered:" + " Gender: " + g + ", Height: " + h + ", Weight: " + w + ", Age: " + a
                    + ", Days: " + d);
    
            double calories = 0;
    
            if (g.equals("Male")) {
                calories = 66 + (6.23 * w) + (12.7 * h) - (6.8 + a);
            }
    
            if (g.equals("Female")) {
                calories = 655 + (4.95 * w) + (6.0 * h) - (4.7 * a);
            }
            if (d == 0) {
                calories = calories * 1.1;
            } else if (d < 3) {
                calories = calories * 1.225;
            } else if (d <= 5) {
                calories = calories * 1.3;
            } else if (d <= 7) {
                calories = calories * 1.525;
            }
            System.out.println(" ");

            System.out.println("Gain 2lbs per week: " + ((int) calories + 1000) + " calories");
            System.out.println("Gain 1.5lbs per week: " + ((int) calories + 750) + " calories");
            System.out.println("Gain 1lb per week: " + ((int) calories + 500) + " calories");
            System.out.println("Gain 0.5lbs per week: " + ((int) calories + 250) + " calories");
            System.out.println("Maintain Current Weight: " + (int) calories + " calories");
            System.out.println("Lose 0.5lbs per week: " + ((int) calories - 250) + " calories");
            System.out.println("Lose 1lb per week: " + ((int) calories - 500) + " calories");
            System.out.println("Lose 1.5lbs per week: " + ((int) calories - 750) + " calories");
            System.out.println("Lose 2lbs per week: " + ((int) calories - 1000) + " calories");

        }

if (whichFunction.equals("Max")){
    System.out.println(" ");
    System.out.println ("Enter Weight Lifted (lbs)");
    int weight = StdIn.readInt();

    System.out.println ("Enter Reps Performed");
    int reps = StdIn.readInt();

    int max;

    max = (int) (weight * reps * 0.0333 + weight);
    System.out.println("Your 1 rep max is: " + max + " lbs");
}

if (whichFunction.equals("Water")){
System.out.println(" ");
System.out.println("Enter: Weight (lbs)");
int weightforwater = StdIn.readInt();
weightforwater = (int) (weightforwater * 2/3);
System.out.println("You should drink: " + weightforwater + " ounces of water per day");
}

if (whichFunction.equals("Macronutrients")){

            System.out.println("Enter: Gender (Male or Female)");
            String g = StdIn.readString();
            System.out.println("Enter: Height (inches)");
            int h = StdIn.readInt();
            System.out.println("Enter: Weight (lbs)");
            int w = StdIn.readInt();
            System.out.println("Enter: Age (years)");
            int a = StdIn.readInt();
            System.out.println("Enter: Days of Exercise Per Week (0-7)");
            int d = StdIn.readInt();
            System.out.println(" ");
            System.out.println("Enter: ''Bulking'' , ''Maintaining'' , or ''Cutting'' based on your weight goal");
            String bmc = StdIn.readString();
            System.out.println(" ");
        
            double calories = 0;
    
            if (g.equals("Male")) {
                calories = 66 + (6.23 * w) + (12.7 * h) - (6.8 + a);
            }
    
            if (g.equals("Female")) {
                calories = 655 + (4.95 * w) + (6.0 * h) - (4.7 * a);
            }
            if (d == 0) {
                calories = calories * 1.1;
            } else if (d < 3) {
                calories = calories * 1.225;
            } else if (d <= 5) {
                calories = calories * 1.3;
            } else if (d <= 7) {
                calories = calories * 1.525;
            }
            int carbs = 0;
            int protein = 0;
            int fat = 0;

        if (bmc.equals("Bulking")){
            calories = calories + 750;
            carbs = (int) (calories * 0.40)/4;
            protein = (int) (calories * 0.30)/4;
            fat = (int) (calories * 0.30)/9;

            System.out.println("Daily Carbs: " + carbs + " grams");
            System.out.println("Daily Protein: " + protein + " grams");
            System.out.println("Daily Fat: " + fat + " grams");
        }

        if (bmc.equals("Cutting")){
            calories = calories - 750;
            carbs = (int) (calories * 0.40)/4;
            protein = (int) (calories * 0.40)/4;
            fat = (int) (calories * 0.20)/9;

        System.out.println("Daily Carbs: " + carbs + " grams");
        System.out.println("Daily Protein: " + protein + " grams");
        System.out.println("Daily Fat: " + fat + " grams");
        }
    
        if (bmc.equals("Maintaining")){
            calories = calories + 0;
            carbs = (int) (calories * 0.35)/4;
            protein = (int) (calories * 0.35)/4;
            fat = (int) (calories * 0.30)/9;

        System.out.println("Daily Carbs: " + carbs + " grams");
        System.out.println("Daily Protein: " + protein + " grams");
        System.out.println("Daily Fat: " + fat + " grams");
        }
}

if(whichFunction.equals("Days")){
    System.out.println("Enter Your Current Weight (lbs)");
    int currentweight = StdIn.readInt();
    System.out.println("Enter Your Goal Weight (lbs)");
    int goalweight = StdIn.readInt();
    if (goalweight > currentweight){
        int poundsuntilgoal = goalweight - currentweight;
        int quickerdaysuntilgoal = (poundsuntilgoal * 7) / 2;
        int slowerdaysuntilgoal = (poundsuntilgoal * 7) * 2;
        System.out.println("Depending on your daily calorie intake you can reach your goal in " + quickerdaysuntilgoal + " - " + slowerdaysuntilgoal + " days");
    }
    if (goalweight < currentweight){
        int poundsuntilgoal = currentweight - goalweight;
        int quickerdaysuntilgoal = (poundsuntilgoal * 7) / 2;
        int slowerdaysuntilgoal = (poundsuntilgoal * 7) * 2;
        System.out.println("Depending on your daily calorie intake you can reach your goal in " + quickerdaysuntilgoal + " - " + slowerdaysuntilgoal + " days");
    }
    if (goalweight == currentweight){
    System.out.println("Congratulations, you have achieved your goal weight!");
    }
}

if (whichFunction.equals("Burned")){
    System.out.println("Type ''Walking'' , ''Running'' , ''Biking'' , or ''Swimming''' depending on what cardiovascular exercise you did");
String whichCardio = StdIn.readString();

if(whichCardio.equals("Walking")){
    System.out.println("Enter: Current Weight (lbs)" );
    int poundsWeight = StdIn.readInt();
    System.out.println("Enter: Distance Walked (miles)");
    double distance = StdIn.readDouble();

double perMile = poundsWeight * 0.49;
double caloriesBurned = perMile * distance; 
System.out.println("You burned " + caloriesBurned + " calories");
}

if(whichCardio.equals("Running")){
    System.out.println("Enter: Current Weight (lbs)" );
    int poundsWeight = StdIn.readInt();
    System.out.println("Enter: Distance Ran (miles)");
    double distance = StdIn.readDouble();

double perMile = poundsWeight * 0.71;
double caloriesBurned = perMile * distance; 
System.out.println("You burned " + caloriesBurned + " calories");
}

if(whichCardio.equals("Swimming")){
    System.out.println("Enter: Time Spent Swimming (hours)" );
    double timeSpentSwimming = StdIn.readDouble();
double caloriesBurned = timeSpentSwimming * 700;
System.out.println("You burned " + caloriesBurned + " calories");
}

if(whichCardio.equals("Biking")){
    System.out.println("Enter: Time Spent Biking (hours)" );
    double timeSpentBiking = StdIn.readDouble();
double caloriesBurned = timeSpentBiking * 550;
System.out.println("You burned " + caloriesBurned + " calories");
}
    }  
 }
}
