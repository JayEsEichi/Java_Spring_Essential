# 7. 인터페이스를 활용한 학점 산출 프로그램 만들기

## 문제 정의

- Good School 학교가 있습니다. 이 학교에는 5명의 학생들이 수업을 듣습니다. 과목은 국어와 수학이 있고, 각 학생은 두 과목을 모두 수강합니다. 

전공은 컴퓨터공학과 국어국문학 두 가지가 있습니다. 컴퓨터공학과 학생은 수학이 필수과목이고, 국어국문학과 학생은 국어가 필수 과목입니다. 

각 학생별로 한 개의 전공을 선택합니다. 

이번 학기 각 학생의 성적은 다음과 같습니다.

| 이름 | 학번 | 전공 | 필수 과목 | 수학 점수 | 국어 점수 |
| ------ | ------ | ------ | ------ | ------ | ------ |
| 강감찬 | 211213 | 국어국문학과 | 국어 | 95 | 56 |
| 김유신 | 212330 | 컴퓨터공학과 | 수학 | 95 | 98 |
| 신사임당 | 201518 | 국어국문학과 | 국어 | 100 | 88 |
| 이순신 | 202360 | 국어국문학과 | 국어 | 89 | 95 |
| 홍길동 | 201290 | 컴퓨터공학과 | 수학 | 83 | 56 |

- 학점을 부여하는 방벅은 여러 가지가 있습니다. 단순히 A,B,C,D,F를 부여하는 방법, A+, B-처럼 +/-를 사용하는 방법, Pass/Fail 만을 부여하는 방법등이 있습니다. 

여기 각 학생에게 학점을 부여하는 데 사용하는 정책은 두 가지입니다. 일반 과목이라면 A ~ F로, 필수 과목이라면 S ~ F 로 분류합니다. 점수에 따른 학점 부여기준은 

다음과 같습니다

- 필수 과목 학점 기준

| S | A | B | C | D | F |
| ------ | ------ | ------ | ------ | ------ | ------ |
| 95~100점 | 90~94점 | 80~89점 | 70~79점 | 60~69점 | 60점 미만 |

- 일반 과목 학점 기준

| A | B | C | D | F |
| ------ | ------ | ------ | ------ | ------ |
| 90~100점 | 80~89점 | 70~79점 | 55~69점 | 55점 미만 |

만약 똑같이 95점을 받은 경우, 필수 과목이라면 S를 받지만, 일반 과목은 A를 받습니다. 또한 56점을 받으면 필수 과목은 F이지만, 일반 과목은 D를 받습니다.

- 프로그램 구현 과제

위와 같이 주어진 성적과 각 과목에 대한 학점 정책에 따라 아래와 같이 학점 결과가 나올 수 있도록 구현합니다.

학점의 정책이 추가되는 경우와 과목이 추가되는 경우를 고려하여 객체를 설계하고 학점 정책에 대해서는 인터페이스를 선언하고 각 정책이 해당 인터페이스를 구현하도록 합니다. 

국어 과목 결과 

![korgrade](./img/korgrade.png)

수학 과목 결과

![mathgrade](./img/mathgrade.png)


## 클래스 정의 하고 관계도 그리기

![student](./img/student.png)

Student.java

```
public class Student {
	
	private int studentId;    		//학번
	private String studentName;		//이름
	private Subject majorSubject;	//중점 과목
	
	//학생의 성적 리스트 
	//addSubjectSocre() 메서드가 호출되면 리스트에 추가 됨
	private ArrayList<Score> scoreList = new ArrayList<Score>(); 
	
	public Student( int studentId, String studentName, Subject majorSubject){
		this.studentId = studentId;
		this.studentName = studentName;
		this.majorSubject = majorSubject;
	}
	
	public void addSubjectScore(Score score){
		scoreList.add(score);
	}

	public int getStudentId() {
		return studentId;
	}

	public void setStudentId(int studentId) {
		this.studentId = studentId;
	}

	public String getStudentName() {
		return studentName;
	}

	public void setStudentName(String studentName) {
		this.studentName = studentName;
	}

	public Subject getMajorSubject() {
		return majorSubject;
	}

	public void setMajorSubject(Subject majorSubject) {
		this.majorSubject = majorSubject;
	}

	public ArrayList<Score> getScoreList(){
		return scoreList;
	}
	
	public void setScoreList(ArrayList<Score> scoreList) {
		this.scoreList = scoreList;
	}
}
```

Subject.java
```
public class Subject {
	private String subjectName;  //과목 이름
	private int subjectId;      // 과목 고유번호
	private int gradeType;      // 과목 평가 방법 기본은 A,B 방식
	
	//수강 신청한 학생 리스트
	//register() 메서드를 호출하면 리스트에 추가 됨
	private ArrayList<Student> studentList = new ArrayList<Student>();
	
	public Subject(String subjectName, int subjectId){
		this.subjectName = subjectName;
		this.subjectId = subjectId;
		this.gradeType = Define.AB_TYPE;   //기본적으로 A, B 타입
	}

	public String getSubjectName() {
		return subjectName;
	}

	public void setSubjectName(String subjectName) {
		this.subjectName = subjectName;
	}

	public int getSubjectId() {
		return subjectId;
	}

	public void setSubjectId(int subjectId) {
		this.subjectId = subjectId;
	}

	public ArrayList<Student> getStudentList() {
		return studentList;
	}

	public void setStudentList(ArrayList<Student> studentList) {
		this.studentList = studentList;
	}

	public int getGradeType() {
		return gradeType;
	}

	public void setGradeType(int gradeType) {
		this.gradeType = gradeType;
	}

	public void register(Student student){  //수강신청
		studentList.add(student);
	}
}
```

Score.java
```
public class Score {
	int studentId;   //학번
	Subject subject; //과목
	int point;      //점수
	
	public Score( int studentId, Subject subject, int point){
		this.studentId = studentId;
		this.subject = subject;
		this.point = point;
	}

	public int getStudentId() {
		return studentId;
	}

	public void setStudentId(int studentId) {
		this.studentId = studentId;
	}

	public Subject getSubject() {
		return subject;
	}

	public void setSubject(Subject subject) {
		this.subject = subject;
	}

	public int getPoint() {
		return point;
	}

	public void setPoint(int point) {
		this.point = point;
	}

	public String toString(){
		return "학번:" + studentId + "," + subject.getSubjectName() + ":" + point;
	}
}
```

Define.java
```
public class Define {

	public static final int KOREAN = 1001;  //국어
	public static final int MATH = 2001;    //수학
		
	public static final int AB_TYPE = 0;    // A, B, C
	public static final int SAB_TYPE = 1;   // S, A, B, c
	public static final int PF_TYPE = 2;   // P, F
	
}
```



## 학점 평가 정책 설계하고 구현하기

- 인터페이스 정의하기

점수에 따른 학점의 정책은 여러가지가 있을 수 있습니다. 인터페이스를 먼저 선언하고, 각 정책 클래스가 이를 구현하도록 합니다

GradeEvaluation.java
```
public interface GradeEvaluation {
	public String getGrade(int point);
}
```




## 프로그램 테스트 하기




## 프로그램 업그레이드 하기
