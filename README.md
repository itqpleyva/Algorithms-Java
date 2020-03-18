# Algorithms-Java
Repo to share some Java Algorithms


package Algorithms;

import java.util.ArrayList;
import java.util.List;

public class AlgorithmsMain {

	public static void main(String[] args) {
	
	//Algorithm to print given one array of 5 elements the mayor sum of 4 elements and the minor sum of 4 elements
	
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
//algorithm to print given array, three values:
				1- number of positive elements/array.size()
				2- number of negative elements/array.size()
				3- number of zeros elements/array.size()
				
		System.out.println("algorithm to print given array, three values:\r\n" + 
				"1- number of positive elements/array.size();\r\n" + 
				"2- number of negative elements/array.size();\r\n" + 
				"3- number of zeros elements/array.size();");

		int[] arr = {-1, -2, 0, 4, 5};
		
		List<Integer> list = new ArrayList<Integer>();
		
		for(int number: arr){
			
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

//Algorithm to print a stair of # given a number of steps

		System.out.println("Algorithm to print a stair of # given e number of steps");//steps = 6;

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

	}

}
