class Fraculator {

        static int Fraculator(int a, int b) {
            if (a == 0)
                return b;
            return Fraculator(b % a, a);
        }
        static void lowest(int den3, int num3) {

            int common_factor = Fraculator(num3, den3);

            den3 = den3 / common_factor;
            num3 = num3 / common_factor;
            System.out.println(num3 + "/" + den3);
        }

        static void addFraction(int num1, int den1,
                                int num2, int den2) {
            int den3 = Fraculator(den1, den2);

            den3 = (den1 * den2) / den3;

            int num3 = (num1) * (den3 / den1) + (num2) * (den3 / den2);

            lowest(den3, num3);
        }

        public static void main(String[] args) {
            int num1 = 1, den1 = 2, num2 = 1, den2 = 4;
            System.out.print(num1 + "/" + den1 + " + " + num2 + "/" + den2 + " = ");
            addFraction(num1, den1, num2, den2);
        }
    }

