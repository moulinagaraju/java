public class Main
{
    public static void main(String args [])
    {
        try {
              int a=10;
              int b=0;
              int result=a/b; 
      System.out.println("result:"+result);
        } 
        catch(ArithmeticException e) 
        {
            System.out.println("can't devide by zero");
        }
        }
}
