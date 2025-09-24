import java.io.IOException;

class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String message) {
        super(message);
    }
}

class EasyExceptionDemo {

    public static void main(String[] args) {
        try {
            int result = 10 / 0;
        } catch (ArithmeticException e) {
            System.out.println("Caught arithmetic: " + e.getMessage());
        }

        try {
            int[] arr = {1, 2, 3};
            System.out.println(arr[2]);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Caught array: " + e.getMessage());
        }

        try {
            withdraw(700, 500);
        } catch (InsufficientFundsException e) {
            System.out.println("Caught custom: " + e.getMessage());
        }

        try {
            readFile("non_existent.txt");
        } catch (IOException e) {
            System.out.println("Caught IOException: " + e.getMessage());
        }
    }

    public static void withdraw(double balance, double amount) throws InsufficientFundsException {
        if (amount > balance) {
            throw new InsufficientFundsException("Not enough balance! Available: " + balance);
        }
        System.out.println("Withdrawal successful");
    }

    public static void readFile(String filename) throws IOException {
        throw new IOException("Error reading file: " + filename);
    }
}
