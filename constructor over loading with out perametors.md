class A {
    int l, b;

    A() {
        l = 10;
        b = 20;
    }

    int area() {
        return l * b;
    }
}

class constructordemo {
    public static void main(String args[]) {
        A a1 = new A();
        int r = a1.area();
        System.out.println("The area is: " + r);
    }
}
