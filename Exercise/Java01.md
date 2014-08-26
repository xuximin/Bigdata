###Java01练习题
###选择题
1. C
2. D
3. B
4. C
5. D
6. D!C
7. A
8. A!D
9. D
10. C!D
11. C
12. D
13. D
14. A
15. A!B
16. A!D
17. D
18. A
19. C(题有问题)
20. D
21. A
22. AD

###填空题
1. float型3.14156
2. 7
3. 4
4. i+j+k=1055

###编程题
1. 定义两个整型变量n1,n2。当n1=22，n2=64时计算输出n1+n2，n1-n2，n1*n2，n1/n2，n1%n2的值。

        public class Java01Test1 {

    	public static void main(String[] args) {
			System.out.println("请输入n1");
			Scanner scanner = new Scanner(System.in);
	  	  String sn1 = scanner.nextLine();
			int n1 = Integer.parseInt(sn1);
			System.out.println("请输入n2");
			String sn2 = scanner.nextLine();
			int n2 = Integer.parseInt(sn2);
			if( n1== 22 && n2 == 64){
				int a = n1+n2;
				System.out.println("n1 + n2 =" + a);
				int b = n1 - n2;
				System.out.println("n1 - n2 =" + b);
				int c = n1 * n2;
				System.out.println("n1 *  n2 =" + c);
				double d = n1/n2;
				System.out.println("n1 / n2 =" + d);
				int e = n1%n2;
				System.out.println("n1 + n2 =" + e);
				scanner.close();
			}else{
				System.out.println("Error!");
			}
	    }
        }
2. 定义两个整型变量n1,n2并赋给任意值。计算输出n1>n2，n1<n2，n1-n2>=0，n1-n2<=0，n1%n2= =0的值。

        public class Java01Test2 {

	    public static void main(String[] args) {
			System.out.println("请输入n1");
			Scanner scanner = new Scanner(System.in);
			String sn1 = scanner.nextLine();
			int n1 = Integer.parseInt(sn1);
			System.out.println("请输入n2");
			String sn2 = scanner.nextLine();
			int n2 = Integer.parseInt(sn2);
			boolean a = n1 > n2;
			System.out.println("n1 > n2 = " + a);
			boolean b = n1 < n2;
			System.out.println("n1 < n2 = " + b);	
			boolean c = (n1 - n2) >= 0;
			System.out.println("((n1 - n2)  >= 0) = " + c);
			boolean d = (n1 - n2) <=0;
			System.out.println("((n1 > n2) <= 0) = " + d);
			boolean e = (n1 % n2) == 0;
			System.out.println("((n1 % n2) == 0) = " + e);
			scanner.close();
	     }
    	   }


3. 定义两个float 变量C、F。计算公式C=5/9（F-32），计算当F=60、F=90时，输出C 的值。

         public class Java01Test3 {
	    	public static void main(String[] args) {
				System.out.println("请输入C");
				Scanner scanner = new Scanner(System.in);
				String sf = scanner.nextLine();
				float F = Float.parseFloat(sf);
				float C = (5.0 / 9) * ( F - 32 );
				System.out.println("C =  " +C);
				scanner.close();
			}
		}

4.  计算圆的周长和面积，设圆的半径为1.5，输出圆的周长和面积值。
        public class Java01Test4 {

			public static void main(String[] args) {
				double r = 1.5;
				double e = 3.14;
				double l = 2 * e * r;
				double s = e * r * r;
				System.out.println("圆的面积为："+s);
				System.out.println("圆的周长为：" +l);

			}
		}