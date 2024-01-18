# java_05_controll
package ch05_controll;

import java.util.Scanner;

public class LoopWhile {

	public static void main(String[] args) {
		// while(조건) 조건이 true이면 반복(무한루프 조심해야함.)
		int i = 1;
		while (i <= 10) {
			System.out.println(i);
			i++;
		}
		int j = 1;
		while (true) {
			System.out.println(j);
			j++;
			if (j == 10) {
				break;
			}
		}
		Scanner scanner = new Scanner(System.in);
		boolean flag = true;
		while (flag) {
			System.out.println("======================");
			System.out.println("이름을 입력하세요(종료 q)");
			System.out.print(">>>");
			String nm = scanner.nextLine();
			// equals 문자열이 같은지 비교 숫자와 달리 String은 ==(x), equals
			if (nm.equals("q")) {
				flag = false;
				System.out.println("종료 하겠습니다");
			} else {
				System.out.println(nm + "님 환영합니다");
			}
			System.out.println("======================");
		}

		// do-while 문
		// 최소 한번은 실행
		boolean isRun = false;
		do {
			System.out.println("hi"); // 최소 1번은 실행
		} while (isRun);

		// 반복문 Labe1 활용
		int x = 0;
		outerLoop: while (x < 5) {
			int y = 0;
			while (y < 5) {
				if (x * y > 6) {
					System.out.println("breaking !");
					System.out.println("x:" + x + "y:" + y);
//					break; // 내부 반복문만 중단되어 다시 메인루프는 진행됨.
					break outerLoop;
				}
				y++;
			}
			x++;
		}
		// while 문을 활용하여 구구단 2~9단을 출력하시오
		int dan = 2;
		int su = 1;
		while (dan <= 9) {
			while (su <= 0) {

			}
		}

	}

}


package ch05_controll;

import java.util.Scanner;

public class Ch05_Ex02 {

	public static void main(String[] args) {
		// 메뉴를 입력받아 가격을 출력(switch사용)
		// 아아 or 아이스아메리카노 :3000
		// 라떼:4500
		// 에스프레소:2500
		// 위의 미뉴로 입력하면 "입력 메뉴 000은 000원 입니다."출력
		// 없는 메뉴면 "저희 메장에 없는 메뉴입니다." 출력
		int salePrice=0;
		Scanner scan =new Scanner(System.in);
		System.out.println("메뉴를 주문하세요");
		System.out.print(">>>");
		String menu= scan.nextLine();
        //위의 조건으로 아래 프로그램을 완성하시오
		switch(menu) {
		case"아아":
		case"아이스아메리카노":
			System.out.println("입력 메뉴는 3000 원입니다");
			break;
		case"라떼":
		    System.out.println("입력 메뉴는 4500원 입니다");
		    break;
		case"에스프레소:2500":
			System.out.println("입력 메뉴는 2500원 입니다");
			break;
		default: // 그밖에
			System.out.println("저희 메장에 없는 메뉴입니다.");
			
		}
	
	
	}

}

package ch05_controll;

/**
 * Class Name : OperatorMain2024. 1. 3. Author : Kimgichan Created Date: 2024.
 * 1. 3. Version : 1.0 Purpose : operator study Descitption : if 와 조건문
 */
public class Conditonal {
	// 전역변수
	// class 중괄호 안에 어디서든 사용가능
	static String subject = "조건문";

	public static void main(String[] args) {
		int price = 30000;
		int mymoney = 10000;
		// 조건문 if문

		if (mymoney > price) {
			System.out.println("돈이 부족함.");
		}
		System.out.println("==");
		String msg;
		// 변수의 사용 범위(scope)
		// 중괄호 블록{} 내부에 선언된 변수는 중괄호 바깥에서 사용할 수 없음.
		if (mymoney < price) {
//		String msg="돈이 부족함"; 중괄호 안에서 선언된 벼수는 밖에서 사용못함.	
			msg = "돈이 부족함";
		} else {
			msg = "돈이 부족함";
		}
		System.out.println(msg);
		// 조건이 1개이상일 경우
		int score = 85;
		String grade = "";
		if (score >= 90) { // 조건1
			grade = "A";
		} else if (score >= 80) { // 조건2
			grade = "B";
		} else if (score >= 70) { // 조건3
			grade = "c";
		} else { // 그밖에
			grade = "E";
		}
		System.out.println(grade);

		// 순서에 주의해야함.
		score = 92;
		if (score >= 80 && score < 90) {
			grade = "B";
		} else if (score >= 90) {
			grade = "A";
		}
		System.out.println(grade);
		boolean flag = true;
		if (flag) {
			msg = "if문 1번쨰 조건식";
		} else {
			msg = "그밖에";
		}
		System.out.println(msg);
		// 중첩 if 문 (if안에 if)
		// 조건1: 이름은 1글자 이상
		// 조건2: 전화번호는 10 or 11자리
		// 조건3: 나이는 14세이상
		String nm = "";
		String phone = "";
		int age = 20;
		// 이름조건
		if (nm.length() >= 1) {
			// 전화번호조건
			if (phone.length() == 10 || phone.length() == 11) {
				// 나이조건3
				if (age >= 14) {
//		System.out.println("회원가입 성공");
					msg = "환영합니다";
				} else {
//        System.out.println("회원가입 실패");
					msg = "나이 조건이 만족하지 않음";
				}
			} else {
				msg = "전화번호 조건이 만족하지 않음";
//        	System.out.println("회원가입 실패")		 
			}
			System.out.println("회원가입 실패");
		} else {

			// switch문 단순 값을 매칭하는 경우 사용(코드해석이 쉬움)
			int num = 1;
			switch (num) {
			case 0: // switch(값)이 0일경우
				System.out.println("수강등록");
				break;
			case 1:// switch(값)이 0일경우
				System.out.println("기초 프로그래밍");
				break;
			case 2:
				System.out.println("데이터베이스");
				break;
			default: // 그밖에
				System.out.println("취업관련!");
			}

		}
	}
}

package ch05_controll;

public class LoofFor {

	public static void main(String[] args) {
		int num = 1;
		System.out.println(num++);
		System.out.println(num++);
		System.out.println(num++);
		System.out.println(num++);
		System.out.println(num++);
		System.out.println(num++);
		System.out.println("===========for문========");
		// for 문
		// (1초기화식; 2조건식 ;4증감식
		for (int i = 1; i <= 10; i++) {
			// 3문 실행문
			System.out.println(i);
		}
		// 1~20까지 더하기
		int sum = 0;
		for (int i = 1; i <= 20; i++) {
			System.out.println(i);
			sum += i;
		}
		System.out.println("1~20을 더하면:" + sum);
		// 21부터 45까지 더하기
		int sum2 = 0;
		for (int i = 21; i <= 45; i++) {
			sum2 += i;
		}
		System.out.println("21~45를 더하면:" + sum2);
		// 1부터 40까지중에 짝수만 더 한 값을 출력하시오!
		int sum3 = 0;
		// 1. 1~40 for작성
		// 2. 조건 짝수일 경우 더하기
		// 3. 최종출력
		for (int i = 1; i <= 40; i++) {
			System.out.println(i);
			// 2. 조건 짝수일 경우 더하기
			if (i % 2 == 0) {
				sum3 += i;
			}
			// 3. 최종출력
			System.out.println("1~40까지 중 짝수만 더하면:" + sum3);
			int sum4 = 0;
			// 2씩 증가
			// for(int i=0; i<=40 ; i+=2)
			{
				System.out.println("i 값:" + i);
				sum4 += i;
			}
			System.out.println("1~40까지 중 짝수만 더하면:" + sum4);
		}

		// for문을 이용해서 구구단 2단을 출력하시오

		int dan = 2;
		System.out.printf("구구단%d 단 /n", dan);
		for (int i = 1; i <= 9; i++) {
			System.out.printf("%d x %d = %d /n", dan, i, dan * i);
		}
		// 2~9단 출력
		for (int i = 2; i <= 9; i++) {
			System.out.println(i + "단");
			for (int j = 1; j <= 9; j++) {
//	    		System.out.println(j)
				System.out.printf("%d x %d =%d /n", i, j, i * j);
			}

			System.out.println("*");
			System.out.println("**");
			System.out.println("***");
			System.out.println("****");
			System.out.println("*****");
			String star = "";
			// for(int i=0; i<5 ; i++) {
			star += "*";
			System.out.println(star);
		}
		// 10 부터 1까지 출력
		for (int i = 10; i >= 1; i--) {
			System.out.println(i);
		}
		// break 문
		// 반복문 내에서 break문이 실행되면 "해당 반복문"을 즉시 종료
		int sum5 = 0;
		// 1~n까지 더한 값이 100이상이 되는 지점의 n을 구하시오!.
		for (int i = 1; i < 9999; i++) {
			sum5 += i;
			if (sum5 >= 100) {
				System.out.println("100 이상이되는 n:" + i);
				break;
			}
		}
		// continue
		for (int i = 1; i <= 10; i++) {
			if (i % 2 == 0) {
				continue; // continue를 만나면 건너뜀(아래 명령문을)
			}
			System.out.println(i);
		}
		// 구구단 출력 2~9단
		// 단5, 8단 제외
		for (int i = 2; i <= 9; i++) {
			System.out.println(i + "단");
			for (int j = 1; j <= 9; j++) {
				// System.out.println(j);
				System.out.printf("%d x %d =%d \n ", i, j, i * j);
			}
		}
	//국수공장에서 면을 100cm 뽑고 있는데 5cm 마다 잘라줘야합니다.
		for(int i=0; i<100; i++) {
			System.out.printf("||||||||");
		if(i % 5 == 4) {
			System.out.printf("---------");
		}
		}
		}
	
	
	}
	
	
	
package ch05_controll;

import java.util.Scanner;

public class LoopWhile {

	public static void main(String[] args) {
		// while(조건) 조건이 true이면 반복(무한루프 조심해야함.)
		int i = 1;
		while (i <= 10) {
			System.out.println(i);
			i++;
		}
		int j = 1;
		while (true) {
			System.out.println(j);
			j++;
			if (j == 10) {
				break;
			}
		}
		Scanner scanner = new Scanner(System.in);
		boolean flag = true;
		while (flag) {
			System.out.println("======================");
			System.out.println("이름을 입력하세요(종료 q)");
			System.out.print(">>>");
			String nm = scanner.nextLine();
			// equals 문자열이 같은지 비교 숫자와 달리 String은 ==(x), equals
			if (nm.equals("q")) {
				flag = false;
				System.out.println("종료 하겠습니다");
			} else {
				System.out.println(nm + "님 환영합니다");
			}
			System.out.println("======================");
		}

		// do-while 문
		// 최소 한번은 실행
		boolean isRun = false;
		do {
			System.out.println("hi"); // 최소 1번은 실행
		} while (isRun);

		// 반복문 Labe1 활용
		int x = 0;
		outerLoop: while (x < 5) {
			int y = 0;
			while (y < 5) {
				if (x * y > 6) {
					System.out.println("breaking !");
					System.out.println("x:" + x + "y:" + y);
//					break; // 내부 반복문만 중단되어 다시 메인루프는 진행됨.
					break outerLoop;
				}
				y++;
			}
			x++;
		}
		// while 문을 활용하여 구구단 2~9단을 출력하시오
		int dan = 2;
		int su = 1;
		while (dan <= 9) {
			while (su <= 0) {

			}
		}

	}

}
