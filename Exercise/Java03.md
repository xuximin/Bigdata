###Java练习题 03 

- 写两个方法,其中一个方法可以把某个整数插入到整型数组的特定位置,数组中原有元素向后移动另一个方法能够从整形数组中特定位置删除掉一个元素,数组中原有元素向前移动

		public class Java03Test1 {

		public static void main(String[] args) {
		System.out.println("增加元素请输入1，删除元素请输入2");
		Scanner scanner = new Scanner(System.in);
		int xz = scanner.nextInt();
		if( xz == 1 ){
			System.out.println("请输入要插入的数字：");			
			int n = scanner.nextInt();
			System.out.println("请输入要插入的位置：");
			int addwz= scanner.nextInt();
			add(n, addwz);			
		}else if( xz ==2){
			System.out.println("请输入你要删除元素的位置：");
			int delwz= scanner.nextInt();
			del(delwz);
		}
		scanner.close();

		}	
		public static void add(int x1 , int x2){//x1为输入的数字，x2为插入位置
		int[] arr ={1 ,2 ,6 ,7, 9, 14};		
		int arrlength = arr.length+1;
		for(int i3 = 0; i3 <arrlength-1; i3 ++){
			System.out.print(arr[i3]+" ");
		}
		System.out.println();
		if( x2 < arrlength-1 && x2 >=1){
			int[] arr1 = new int[arrlength];	
			arr1[x2] = x1;
			for(int i = 0 ; i < x2; i ++){
				arr1[i] = arr[i];
			}
			for(int i1 = x2+1; i1 < arrlength; i1++){
				arr1[i1] = arr[i1-1];
			}
			for(int i2 = 0; i2 <arrlength; i2 ++){
			System.out.print(arr1[i2]+" ");
			}
		}else{
			System.out.println("下标越界！");
		}
		}	
		public static void del(int wz){
		int[] arr ={1 ,2 ,6 ,7, 9, 14};
		int arrlength = arr.length-1;
		for(int i4=0;i4<arrlength+1;i4++){
			System.out.print(arr[i4]+"	");
		}
		System.out.println();
		if(wz<= arr.length && wz >=1){			
			int[] arr1 = new int[arrlength];					
				for(int i =0;i<wz;i++){
					arr1[i] = arr[i];
				}				
				for(int i2 =wz; i2 <arrlength+1; i2++){//
					arr1[i2-1] = arr[i2];
				}			
			for(int i3=0;i3<arrlength;i3++){
				System.out.print(arr1[i3]+"	 ");
			}
		}else{
			System.out.println("下标越界！");
		}		
		}	
		}
		
- 有偶数支足球队进行单循环比赛,请按照指定算法打印每轮的对阵形势

		public class Java03Test2 {
		public static void main(String[] args) {
			System.out.println("请输入足球队的支数：");
			Scanner scanner = new Scanner(System.in);
			int n = scanner.nextInt();		
			int[] arr= new int[n];	
			for(int b= 0; b<n; b ++){
				arr[b] = b+1;
			}

			for(int i =1 ; i <arr.length; i++){
				printArray(arr);
				exchangeArray(arr);			
				System.out.println();
			}
			scanner.close();
		}	
		public static void exchangeArray(int[] arrs){		
			int[] arr1 = new int[arrs.length-1];
			int[] arr2 = new int[arrs.length-1];
			for( int i =0 ; i< arr1.length ; i++){
				arr1[i] =arrs[i+1]; 
			}
			arr2[0]=arr1[arr1.length-1];
			for(int j =1;j < arr2.length; j++){
				arr2[j]=arr1[j-1];			
			}
			for(int k =0; k<arr2.length; k++){
				arrs[k+1] = arr2[k];
			}
		}	
		public static void printArray(int[] arrs){
			for(int i = 0 ; i < arrs.length/2 ; i++){
				System.out.print(arrs[i]+" \t");
			}
			System.out.println();
			for(int j = arrs.length; j > arrs.length/2; j --){
				System.out.print(arrs[j-1] + " \t");
			}
			System.out.println();
		}
		}
- 定义一个奇数阶二维数组,把每个元素顺序填入不同的自然数,要求行列和对角线元素相加的结果相等

     	public class Java03Test3 {
		static Scanner scanner = new Scanner(System.in);
		public static void main(String[] args) {
		System.out.println("请输入奇阶幻方阶数：");
		int  n  = scanner.nextInt();
		int[][] arr = new int[n][n];
		fill(arr, n / 2 -1,1 , 1);
		print(arr);
		}
		public static void fill(int[][] arr,int x ,int y , int value  ){
		if(value > arr.length*arr.length){
			return ;
		}
		int nextX =  x + 1;
		int nextY =  y - 1;
		if((nextX > arr.length - 1)  && ( nextY < 0)){//行和列都越界
			nextY = y +1;
			nextX = x;			
		}else if(nextY < 0){//只有行越界
			nextY = arr.length -1;			
		}else if(nextX > arr.length -1){//只有列越界
			nextX = 0;
		}else{
			if( arr[nextY][nextX] != 0){//行和列都不越界,新坐标有值
			nextX = x;
			nextY = y +1;
			}
		}
		arr[nextY][nextX] = value;	
		
		fill(arr, nextX, nextY, ++value);					
		}
		public static void print(int[][] arr){
		for(int i = 0 ; i < arr.length ; i++){
			for(int j = 0; j <arr[i].length; j ++){
				System.out.print(arr[i][j]+ "\t");
			}
			System.out.println();
		}		
		}
		}

- 数学黑洞6174
    已知：一个任意的四位正整数。将数字重新组合成一个最大的数和最小的数相减，重复这个过程，最多七步，必得6174。
    即：7641-1467=6174。将永远出不来。
    求证：所有四位数数字（全相同的除外），均能得到6174。输出掉进黑洞的步数。
	
		public class Java03Test4 {
		public static void main(String[] args) {
		//定义3个数组
		int[] arrin= new int[4];		
		int max = 0;
		int min = 0;
		//获取输入整数
		System.out.println("请输入四位整数：");
		Scanner scanner = new Scanner(System.in);
		int num = scanner.nextInt();
		int sum =0;
		//将整数存放到数组中
		arrInt(num,arrin);
		//一个从大到小排列
		//一个从小到大		
		for(int i = 0 ; i < 7 ; i ++){
			arrMax(arrin);
			max= intnum(arrin);
			arrMin(arrin);
			min = intnum(arrin);
			sum = max - min;						
			if(sum == 0){
				System.out.println("请输入至少一位不同的4位整数！");
			}
			System.out.println(max+"-"+min+"="+sum);
			if(sum == 6174){
				break;
			}
			arrInt(sum, arrin);			
		}
		if(sum != 6174){
			System.out.println("这个结论是错误的！");
		}
		scanner.close();
		}
		//将4位整数存放到数组中
		public static void arrInt(int n,int[] arr){
		int x=10;
		for(int i = 3 ; i >= 0 ; i--){
			arr[i] = n % x ;
			n = n /x;			
		}
		}
		//将数组转换成整数
		public static int intnum(int[] arr){
		int sum = 0;
		int x =1000;
		for(int i = 0; i < arr.length; i++){
			sum = arr[i] * x +sum;
			x = x / 10;
		}
		return sum;
		}
		//从大到小排列数组
		public static void arrMax(int[] arr){
		for(int x  = 0 ; x <arr.length - 1;  x++){
			for(int y = 0 ; y <arr.length - x -1; y ++){
				if(arr[y] < arr[y+1]){
					int temp = arr[y];
					arr[y] = arr[y+1];
					arr[y+1] = temp;
				}
			}
		}
		}
		//从小到大排列数组
		public static void arrMin(int[] arr){
		for(int x  = 0 ; x <arr.length - 1;  x++){
			for(int y = 0 ; y <arr.length - x -1; y ++){
				if(arr[y] > arr[y+1]){
					int temp = arr[y];
					arr[y] = arr[y+1];
					arr[y+1] = temp;
				}
			}
		}
		}
		}


