package Algorithms;

import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
public class AlgorithmsMain {

	public static void main(String[] args) {
	
//Algorithm to print given one array of 5 elements the mayor sum of 4 elements and the minor sum of 4 elements"		

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
		
//Algorithm to print a stair of # given a number of steps"

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

//Algorithm cake candle	

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
		
//Algorithm breaking records

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
		
//Pairs sum divisible by 5 in list

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
		
//Absolute diagonal difference in matrix

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
    }

}
