# Quiz 5 Corrections
## Question 10
Consider the following partially implemented class.

    public class Quiz {

      private static int id = 1;
      private int questionCount;

      public Quiz(int questionCount) {
          this.questionCount = questionCount;
      }

      public int getId() {
          return id;
      }

      public void incrementId() {
          id++;
      }

      public int getQuestionCount() {
          return questionCount;
      }
    }
Now, consider the following usage of the aforementioned class.

    Quiz q1 = new Quiz(10);
    Quiz q2 = new Quiz(15);
    q2.incrementId();
    
    System.out.println(q1.getId());
    System.out.println(q2.getId());
    System.out.println(q1.getQuestionCount());
    System.out.println(q2.getQuestionCount());
What will be printed to the console?

### Answer
The correct answer for this question would be the following option:

    2
    2
    10
    15
When you first start the program, q1 is initialized so that the original questionCount variable is 10 and the id is 1. Similarly, q2 is initialized so that the original questionCount variable is 15 and the id is 1. Immediately after, the incrementId() method is called, which increments q2's id by 1, making it 2. However, since id is a static variable, changing the variable value for one object changes it for all objects of that class, causing q1's id to also become 2. This is why when printing the ids of each of the Quiz objects, you get 2 for both. The print statements following this ask to print the result of the getQuestionCount() for each of the Quiz objects. questionCount is not a static variable, so its value for each of the objects can be different. Since q1 was intialized with 10 as the questionCount value, the getQuestionCount() method for q1 returns 10, which is printed to the console. Similarly, since q2 was initialized with a questionCount value of 15, the getQuestionCount() method for q2 returns 15, which is printed out to the console. Taken as a whole, the output to the console would be:

    2
    2
    10
    15
