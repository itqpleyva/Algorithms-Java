
public class AlgorithmsMain {

	public static void main(String[] args) {
		
		// If integer is palindrome solution 1
		
		List<Integer> kl = new ArrayList<Integer>();
		int cv = 121;
		int length = (int) (Math.log10(cv + 1));
		int tmpl = cv;
		int result = 0;
		for(int i = 0; i < length+1; i++) {
			
			kl.add(tmpl%10);

			tmpl=tmpl/10;
		}
		for(int i = 0; i < length+1; i++) {
			result*=10;
			result+=kl.get(i);
		}
		System.out.println(cv == result?"Palindrome":"No palindrome");
		
		
		// If integer is palindrome solution 2
		
		Integer vb = Integer.valueOf(cv);

		
		Integer mn =  IntStream.iterate (vb, i -> i/10)
								.limit(10)
								.filter (i -> i != 0)
								.map(i -> i % 10)
								.reduce (0, (subtotal,element) -> subtotal*10 + element);
		
		System.out.println("original " +vb);
		System.out.println("reversed " +mn);
		if (cv == mn) {
			System.out.println("palindrome");
			
		}
		else {
			
			System.out.println("no palindrome");
			
		}
		
		//Sum of inverted linked list
			
		LinkedList<Integer> linkedList1 = new LinkedList<Integer>(Arrays.asList(2,4));
		LinkedList<Integer> linkedList2 = new LinkedList<Integer>(Arrays.asList(5,6,4));
		List<Integer> listaa = new ArrayList<Integer>();
		String number1= "";
		String number2= "";
		
		if (linkedList1.size() == linkedList2.size()) {
			for (int i = linkedList1.size()-1; i >= 0; i--) {
				number1=number1.concat(linkedList1.get(i).toString());
				number2=number2.concat(linkedList2.get(i).toString());
			}
		}
		else {
			for (int i = linkedList1.size()-1; i >= 0; i--) {
				number1=number1.concat(linkedList1.get(i).toString());
			}
			for (int i = linkedList2.size()-1; i >= 0; i--) {
				number2=number2.concat(linkedList2.get(i).toString());
			}		
			
		}
		System.out.println(Integer.parseInt(number1)+Integer.parseInt(number2));
		
		//if chains of characters is valid
		
		String ss = "({(})";
		Map<Character,Character> characterMap = new HashMap<Character,Character>();
		Stack<Character> pila = new Stack<Character>();
		characterMap.put(')','(');
		characterMap.put(']','[');
		characterMap.put('}','{');
		
	    for (int i = 0; i < ss.length(); i++) {
	        char c = ss.charAt(i);

	        // If the current character is a closing bracket.
	        if (characterMap.containsKey(c)) {

	          // Get the top element of the stack. If the stack is empty, set a dummy value of '#'
	          char topElement = pila.empty() ? '#' : pila.pop();

	          // If the mapping for this bracket doesn't match the stack's top element, return false.
	          if (topElement != characterMap.get(c)) {
	            break;
	          }
	        } else {
	          // If it was an opening bracket, push to the stack.
	          pila.push(c);
	        }
	      }
	    System.out.println(pila.isEmpty());
		
		
		//get the position of the two integers (int a + int b = int expected
		int[] arrayTest = {2,3,7,4,8};
		Map<Integer,Integer> map = new HashMap<Integer,Integer>();
		
		int expected = 6;
		int[] arrayToreturn= new  int[2];
		
		for (int i = 0; i < arrayTest.length; i++) {
			
			int delta = expected - arrayTest[i];
			
			if (map.containsKey(delta)) {
				arrayToreturn[0]=i;
				arrayToreturn[1]=map.get(delta);
			}
			map.put(arrayTest[i], i);
		}		
		System.out.println(arrayToreturn[0]+"---"+arrayToreturn[1]);

		//FizzBuzz
		
		for (int i = 0; i <= 100; i++) {
			if(i%3==0 && i%5==0) {
				System.out.println("FizzBuzz");
			}
			else if(i%3==0) {
				System.out.println("Fizz");
			}
			else if(i%5==0) {
				System.out.println("Buzz");
			}
			else
				System.out.println(i);
			
		}
		//Ana and Carlos bill algorithm 
		int nC= 1;
		
		Integer[] bill1 = {3,10,2,9};
		
		List<Integer> bill = Arrays.asList(bill1);
		
		int pagado = 2;
		int realDebe = 0;
		
		for (int j = 0; j < bill.size(); j++) {
			
			if(j != nC) {
				realDebe = realDebe + bill.get(j);				
			}
		}
		realDebe = pagado - (realDebe/2);
		if (realDebe == 0) {
			System.out.println("Bone Appetit");
		}
		else
		System.out.println("Anna debe : "+realDebe);
		
		//Valleys walk algorithm
		
		    String s = "DDUUUUDDDUDU";
		    int level= 0;
		    int valleys = 0;
		    String last = "";

				
				for (int j = 0; j < s.length(); j++) {
				
					if (String.valueOf(s.charAt(j)).equals("U")) {
						level++;
					}
					else {
						level--;					
					}
					last = String.valueOf(s.charAt(j));
					
					if (level == 0 && last.equals("U")) {
						valleys++;
					}
				
				}
				System.out.println("Number of valleys = "+ valleys);
				
			//"Algorithm to print given one array of 5 elements the mayor sum of 4 elements and the minor sum of 4 elements"
        
		System.out.println("Algorithm to print given one array of 5 elements the mayor sum of 4 elements and the minor sum of 4 elements");
		int[] arrs = {1,2,3,4,5};
		
		int cont1=0;
		int cont2=0;
		Long menorsum= (long) 0;
		Long mayorsum= (long) 0;
		int sum =  0;
		
		List<Integer> tt = new ArrayList<Integer>();
		
		for (Integer longer : arrs) {
			tt.add(longer);
		}
		
		Long menor = tt.stream().mapToLong(i -> i).min().orElse(0);
		Long mayor = tt.stream().mapToLong(i -> i).max().orElse(0);
		
		if (menor != mayor) {
			for (int value : tt) {
				if (value == menor && cont1 > 0) {
					menorsum = menorsum + value;
				}
				if (value == menor && cont1 == 0) {

					cont1++;
				}
				if (value != menor) {
					menorsum = menorsum + value;
				}			
			}
			for (int value : tt) {
				if (value == mayor && cont2 > 0) {
					mayorsum = mayorsum + value;
	
				}
				if (value == mayor && cont2 == 0) {

					cont2++;
				}
				if (value != mayor) {
					mayorsum = mayorsum + value;
				}
			}		
			System.out.println(mayorsum+" "+menorsum);
		} else {
			
			for (int j = 0; j < tt.size()-1; j++) {
				sum = sum + tt.get(j);
			}
		
			System.out.println(sum +" "+ sum);
		}
		
		//"algorithm to print given array, three values:\r\n" + 
		//"1- number of positive elements/array.size();\r\n" + 
		//"2- number of negative elements/array.size();\r\n" + 
		//"3- number of zeros elements/array.size();"
		
		System.out.println("algorithm to print given array, three values:\r\n" + 
				"1- number of positive elements/array.size();\r\n" + 
				"2- number of negative elements/array.size();\r\n" + 
				"3- number of zeros elements/array.size();");

		int[] arrq = {-1, -2, 0, 4, 5};
		
		List<Integer> list = new ArrayList<Integer>();
		
		for(int number: arrq){
			
			list.add(number);
		}
				
		long negativ = list.stream().filter(a->a<0).mapToInt(a->a).count();
		long positive = list.stream().filter(a->a>0).mapToInt(a->a).count();
		long cero = list.stream().filter(a->a==0).mapToInt(a->a).count();
		
		double pos = (double) positive/(double) list.size();;
		double neg = (double) negativ/(double) list.size();
		double cer = (double) cero/(double) list.size();
		
		System.out.println(pos);
		System.out.println(neg);
		System.out.println(cer);
		
		//"Algorithm to print a stair of # given a number of steps"
		
		System.out.println("Algorithm to print a stair of # given a number of steps");//steps = 6;

		int n = 0;
		int m = 0;
		int tmp = 6;
		int tmp1 = 6;
		String cha = "#";
		String space = "";
		
		while (n < tmp) {
			m=1;
			while (m < tmp1 ) {
				space = space.concat(" ");
				m++;
			}		
			String aux = space.concat(cha);
			System.out.println(aux);
			space = "";
			tmp1--;
			n++;
			cha = cha.concat("#");
		}

		//"Algorithm cake candle"
		
		System.out.println("Algorithm cake candle");//print the amount of mayor number in arra
		
		int[] arra = {1111111111,1111111111,1111111111};
		

		List<Integer> lista = new ArrayList<Integer>();
		
		for(Integer valor: arra){
			
			lista.add(valor);
		}
		System.out.println(lista);
		
		Integer biger = lista.stream().max(Integer::compare).get();

	
		int cantidad =  Collections.frequency(lista, biger);

				
		System.out.println(cantidad);
		
		//"Algorithm breaking records"
		
		System.out.println("Algorithm breaking records");
		
		int[] scores= {10,34,11,23,4,56,78,3};
		
		List<Integer> listascore = new ArrayList<Integer>();

		for(Integer valor: scores){
			
			listascore.add(valor);
		}
		
		int tempMenor = 0;
		int tempMayor = 0;		
		int countMayorBreak =  0;
		int countMinorBreak = 0;
		
		for (int i = 0; i < listascore.size(); i++) {
			
			if (i==0) {
				tempMayor = listascore.get(i);
				tempMenor = listascore.get(i);
			}
			else {
	
				if (listascore.get(i) > tempMayor) {
					
					tempMayor = listascore.get(i);
					countMayorBreak++;
					//System.out.println("El mayor: "+tempMayor);
				}
				if (listascore.get(i) < tempMenor) {
					
					countMinorBreak++;
					tempMenor = listascore.get(i);
					//System.out.println("El menor: "+tempMenor);
				}
				
			}
			
		}

		int[] rec = {countMayorBreak,countMinorBreak};
		System.out.println(rec[0]+" "+rec[1]);

		//"Pairs sum divisible by 5"
		
		System.out.println("Pairs sum divisible by 5");
	
		int cont = 0;
		int tempNumber = 0;
		int[] numbers= {100,100,100,100,55,32};
		
		
		List<Integer> listaNum= new ArrayList<Integer>();

		for(Integer valor: numbers){
			
			listaNum.add(valor);
		}
		
		for (int i = 0; i < listaNum.size(); i++) {
			tempNumber = listaNum.get(i);
			
			for (int j = 0; j < listaNum.size(); j++) {
				if (i<j) {
					
					int calc = tempNumber + listaNum.get(j);
					if ((calc % 3) == 0) {
						
						cont++;
					}
					
				}
		
			}
		}
		
		System.out.println(cont);
		
		//"Absolute Diagonals Difference in a Matrix"
		
		System.out.println("Absolute Diagonals Difference in a Matrix");

		List<List<Integer>> arr = new ArrayList<List<Integer>>();
	
		 for(int i =0; i<= 4; i++){
		            arr.add(new ArrayList<Integer>());
		        }
		
        arr.get(0).add(11);
        arr.get(0).add(2);
        arr.get(0).add(4);
 
        arr.get(1).add(4);
        arr.get(1).add(5);
        arr.get(1).add(6);
        
        arr.get(2).add(10);
        arr.get(2).add(8);
        arr.get(2).add(-12);
		
        	int len = arr.get(1).size();
        
        int sumFirstD = 0;
        int sumSecondD = 0;
        int contador = 0;
        
        for (int i = 0; i < len; i++) 
        { 
        	sumFirstD += arr.get(i).get(i); 
        	sumSecondD += arr.get(i).get(len-i-1); 
        } 
        System.out.println(Math.abs(sumFirstD-sumSecondD));
        
        //Rounded grades
        
        System.out.println("----------------------------------------------------------------");
        System.out.println("Rounded grades");
      
        
        List<Integer> grades = new ArrayList<Integer>();
        List<Integer> finalGrades = new ArrayList<Integer>();
        
        
        grades.add(73);
        grades.add(67);
        grades.add(38);
        grades.add(33);
        

        grades.forEach(a->{
        	int conTemp = 1;
        	int nextmultiplo=0;
        	boolean ca = true;


        	if (a < 38) {
				nextmultiplo = a;
				finalGrades.add(a);
			}
        	else {
            	while( ca ) {

               	   	if((a + conTemp)%5 == 0) {

            	   		if ((a + conTemp)-a < 3) {
            	   			nextmultiplo = a + conTemp;

    					}
            	   		else {
            	   			
            	   			nextmultiplo = a;

            	   		}
            	   		ca=false;
            	   		System.out.println(nextmultiplo);
            	   		finalGrades.add(nextmultiplo);
            	   			
            	   		   
                	}
               	   	else {
               	   		conTemp++;
               	   	}
                	
            	}
        	}

     
        });
        
        System.out.println(finalGrades);
        
        //Weird Not Weird Algorithm
        
        int N = 8;
        
        if(N % 2 != 0) {
        	
        	System.out.println("Weird");
        }
        else {
        	
        	if(N >=2 && N<=5) {
            	System.out.println("Not Weird");    		
        	}
        	else if(N >=6 && N<=20) {
        		System.out.println("Weird");    		
        	}
        	else if(N >20 ) {
        		System.out.println("Not Weird");    		
        	}
        	

        }

        //print table of products
        
        int o = 2;
        for (int j = 1; j <= 10; j++) {
			
        	System.out.println(o+" x "+j+" = "+o*j);
		}
        
        //================================================= working on
        Scanner in = new Scanner(System.in);
        
        int t=in.nextInt();
        List<Integer> listTest = new ArrayList<Integer>();
        
        for(int i=0;i<t;i++){
            int a = in.nextInt();
            int b = in.nextInt();
            int na = in.nextInt();
 
            for (int j = 1; j <= na; j++) {				
                   	
            	a = a + (int)Math.pow(2,j)*b;
            	
            	System.out.println(a);
			}
            System.out.println("");
        }
        in.close();
    }

}
