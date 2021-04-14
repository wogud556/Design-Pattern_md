디자인패턴 Ref: Youtube 이야기's G 자바 디자인 패턴

## 빌더 패턴 2
---
### 학습목표
- 많은 변수를 가진 객체의 생성을 가독성 높도록 코딩할 수 있다

### 키워드
- 가독성
- 많은 변수의 패턴

### 빌더 패턴
- 많은 인자를 가진 객체를 생성을 다른 객체의 도움으로 생성하는 패턴

### 예제 코드
```
public class Computer{
	private String cpu;
    private String ram;
    private String strage;
	
	/*
	*
	* @param cpu 씨피유 이다
	* @param ram 램 이다
	* @param storage 저장공간 이다
	*/

	public Computer(String cpu, String ram, String strage) {
		super();
		this.cpu = cpu;
		this.ram = ram;
		this.strage = strage;
	}

	public String getCpu() {
		return cpu;
	}
	public void setCpu(String cpu) {
		this.cpu = cpu;
	}
	public String getRam() {
		return ram;
	}
	public void setRam(String ram) {
		this.ram = ram;
	}
	public String getStrage() {
		return strage;
	}
	public void setStrage(String strage) {
		this.strage = strage;
	}

    @Ovrride
    public String toString(){
        return cpu + "," + ram + "," + storage;
    }

	public Computer build(){
		return this.computer;
	}
}

public class Main{
	public static void main(String [] args){
		//Computer computer = new Computer("256g ssd", "i7", "");
		Computer computer = ComputerBuilder
			//	.start()
				.startWithCpu("i7")
				.setCpu("i7")
				.setRam("256g")
				.setStorage("8g")
				.build();

		System.out.println(computer.toString());
	}
}

public class ComputerBuilder{
	private Computer computer
	private ComputerBuilder(){
		computer = new Computer("default","default","default");
	}

	public static ComputerBuilder startWithCpu(){
		ComputerBuilder builder = new ComputerBuilder();
		builder.computer.setCpu(cpu);
		return builder;
	}

	public static ComputerBuilder start (String cpu){
		new ComputerBuilder();
	}

	public ComputerBuilder setCpu(String string){
		computer.setCpu(String);
		return null;
	}

	public ComputerBuilder setStorage(String storage){
		computer.setStorage(storage);
		return this;
	}

	public Computer setRam(String string){
		computer.setRam(string);
		return null;
	}
	

}

```