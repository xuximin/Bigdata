###JAVA02
- 为考试成绩划定五个级别，当成绩大于或等于90分时，划定为优；当成绩大于或等于80且小于90时，划定为良；当成绩大于或等于70且小于80时，划定为中；当成绩大于或等于60且小于70时，划定为及格；当成绩小于60时，划定为差.使用if语句

      public class Java02Test1 {

	   public static void main(String[] args) {
		//优>=90，良<90 &&>=80，中<80 && >=70，及格<70 &&>=60，差<60
		System.out.println("请输入成绩");
		Scanner scanner = new Scanner(System.in);
		String Score = scanner.nextLine();
		int score = Integer.parseInt(Score);
		if(score >= 90){
			System.out.println("恭喜你！你的成绩为优！");
		}else{
			if( score <90 && score >= 80){
				System.out.println("不错哦~你的成绩为良！");
			}else{
				if(score <80 && score >=70){
					System.out.println("再接再厉~你的成绩为中！");
				}else{
					if(score <70 && score >=60){
						System.out.println("你需要努力啊！你刚好及格！");
					}else{
						System.out.println("革命尚未成功，同志仍需努力！你的成绩竟然为差！");
					}
				}
			}
		}
		scanner.close();
	  }

      }
	  
	  
- 使用switch结构重写上面代码

      public class Java02Test2 {

	    public static void main(String[] args) {
			System.out.println("请输入你的成绩");
			Scanner scanner = new Scanner(System.in);
			String Score = scanner.nextLine();
			int score = Integer.parseInt(Score);
			switch(score/10){
			case 9:
				System.out.println("恭喜你！你的成绩为优！");
				break;
			case 8:
				System.out.println("不错哦~你的成绩为良！");
				break;
			case 7:
				System.out.println("再接再厉~你的成绩为中！");
				break;
			case 6:
				System.out.println("你需要努力啊！你刚好及格！");
				break;
			default:
				System.out.println("革命尚未成功，同志仍需努力！你的成绩竟然为差！");
			}
			scanner.close();
		}

	  }
	  
- 给出年份、月份，计算输出该月的天数 使用switch

        public class Java02Test3 {

	    public static void main(String[] args) {
		
		System.out.println("请输入年份");
		Scanner scanner = new Scanner(System.in);
		String Years = scanner.nextLine();
		int year = Integer.parseInt(Years);
		System.out.println("请输入月份");
		String Month = scanner.nextLine();
		int month = Integer.parseInt(Month);
		//判断是否为闰年
		int temp = 0;
		int day = 0;
		switch(year % 400){
		case 0:
			temp=2; //temp =2时为闰年
			
			break;
		default:
			switch(year % 4){
			case 0:
				switch( year % 100){
				case 0:
					temp=1; //temp=1 时不为闰年
					
					break;
				default:
					temp=2;
					
				}
				break;
			}
			break;
		}
		switch(month){
		case 1:
		case 3:
		case 5:
		case 7:
		case 8:
		case 10:
		case 12:
			day = 31;
			System.out.println(year+"年"+month+"月一共有"+day+"天");
			
			break;
		case 4:
		case 6:
		case 9:
		case 11:
			day = 30;
			System.out.println(year+"年"+month+"月一共有"+day+"天");
			break;
		case 2:
			switch(temp){
			case 1:
			case 0:
				day = 28;
				System.out.println(year+"年"+month+"月一共有"+day+"天");
				break;
			default:
				
				day = 29;
				System.out.println(year+"年"+month+"月一共有"+day+"天");
			}
			break;
		default:
				System.out.println("输入错误！");
			}
		
		scanner.close();	
		}
		
	  }
	  
- 计算sum=1+2+3+4+5+…+100 使用for循环

        public class Java02Test4 {

	    public static void main(String[] args) {
			int sum =0;
			for(int i = 1;i < 101; i++){
			sum = sum +i;
			}
		System.out.println("Sum="+sum);
		}

		}
		
- 一对兔子从它出生后第3个月起，每个月都生一对小兔子，小兔子3个月后又生一对小兔子，假设兔子都不死，求每个月的兔子对数。该数列为：
1   1   2   3  5   8   13   21…  即从第3项开始，其该项是前两项之和。求100以内的波那契数列 分别使用for与while循环
  1.for语句：
		public class Java02Test5 {

	    public static void main(String[] args) {
			int y = 1;
			System.out.print(y+" ");
			for(int x = 1;  x< 100; x=x+y ){ //第三项
				y = x + y;
			/**	s1=1
				s2=1
				s3=s1+s2
				s4=s3+s2
				s5=s4+s3
				……
				s100=s99+s98
				*/
				System.out.print(x+" "+y +" ");
			} 
		}
		}
		
	2.while语句
		public class Java02Test502 {

		public static void main(String[] args) {
		int y = 1;
		int x = 1;
			while(true ){
				if(x > 100){
					break;
				}else{
					if(x < 100 && y>100){
						System.out.print(x+" ");
						break;
					}else{
						System.out.print(x+" "+y+" ");
					}
				}				
				x = x + y;				
				y = x + y;
			
	   	 }
		}
		}
		
-  计算n!, 当n=9时。并分别输出1！~9！各阶乘的值 使用while循环

	    public class Java02Test6 {

		public static void main(String[] args) {
		int n = 9;
		int sum =0;
		int i =1;
		while(i <= n){
			sum = i*i;
			System.out.println(i+"！="+sum);
			i++;
			sum = sum + i*i;
			
		}

		}

		}
		
- 输出50~100以内的所有素数。所谓素数即是只能被1和其自身除尽的正整数。

		public class Java02Test7 {
		public static void main(String[] args) {
			for(int n = 50 ;  n < 101 ; n++){								
				int temp = 0;
				for(int i  =2; i< n /2 ; i++){
					if( n % i == 0){					
						temp =1;
						break;	
					}					
				}			
				if( temp == 0){
					System.out.println(n);
				}
				temp = 0;
			}
		}
		}
		
- 输出10~1000之间既能被3整除也能被7整除的数

		public class Java02Test8 {
			public static void main(String[] args) {
				for(int i = 10 ;  i < 1001 ; i ++){
					if( i % 3 ==0 && i % 7 == 0){
						System.out.println(i);
					}
				}
			}
		}

- 判断一个正整数是否是素数，若是计算其阶乘。判断素数和阶乘作为方法定义，并在主方法中调用它们

		public class Java02Test9 {

		public static void main(String[] args) {
		
		System.out.println("请输入数字：");
		Scanner scanner = new Scanner(System.in);
		int sr = scanner.nextInt();
		
		if( sr <= 0  ){//判断输入的是否为正整数
			System.out.println("输入错误！");
		}else{//如果是，判断其是否为素数
			
			if( sr == 1 || prime(sr) == false  ){
				System.out.println("你输入的数字不是素数！");
			}else{//如果是素数，输出其阶乘
				factorial(sr);
			}
		}
		scanner.close();
		
		}
	
		private static boolean prime(int in) {//判断素数的方法		
		int temp = 0; //默认输入的是素数
		for(int i =2; i < in; i ++){
			if( in % i == 0){
				temp =1 ;  //输入的 不是素数
				break;
			}			
		}
		if(temp == 1){
			
			return  false;
		}else{
			if(in == 1){
				
				return   false;
			}else{
				if(in == 0 ){
					
					return   false;
				}else{
					return true;
				}
			}
		}
		}

		public static void factorial(int input) {//阶乘方法
		int sum  =0;
		for(int i = 1; i < input +1; i++){
			sum = i * i+sum;
		}
		System.out.println(input+"! = "+sum);
		}
		}