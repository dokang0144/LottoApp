# LottoApp
안드로이드 스튜디오로 개발한 로또앱<br>
## 실행화면
### 앱을 처음으로 켰을때
![Screenshot_20220721_153007](https://user-images.githubusercontent.com/88234731/180144857-0b4587e4-1f6d-4e6e-98ce-ded3f0a0b48d.png)
* * *
### 로또 번호 생성하기를 클릭했을때
![Screenshot_20220721_153901](https://user-images.githubusercontent.com/88234731/180146741-8a65b17a-cd64-4024-a304-27986e80dd4e.png)
* * *
### 로또 번호를 저장하고 리스트에 들어갔을때
![Screenshot_20220721_153913](https://user-images.githubusercontent.com/88234731/180147578-269a9b5b-e561-45b7-82fb-b4b134cee3f7.png)
* * *
### 로또 번호 중복 허용을 체크하고 로또 번호 생성하기를 클릭했을때
![Screenshot_20220721_153956](https://user-images.githubusercontent.com/88234731/180147827-3e42d92b-3966-4a0f-9d31-6b81e47cc313.png)
* * *
### 처음 저장한 로또 번호와 중복 허용을 체크하고 저장한 로또 번호가 저장되어있습니다
![Screenshot_20220721_154006](https://user-images.githubusercontent.com/88234731/180147847-66f89f03-5137-41d0-8cbe-70556863786b.png)

## 소스코드

```kotlin
//로또 번호를 중복을 허용하고 생성하는 함수
private fun getLottoNumber1() {
	val rnd = Random()
	val lotto = IntArray(6)
	for (i in lotto.indices) {
		lotto[i] = rnd.nextInt(45) + 1
	}
	lotto.sort()
	setTvNumber(lotto[0], binding.tvLotto1)
	setTvNumber(lotto[1], binding.tvLotto2)
	setTvNumber(lotto[2], binding.tvLotto3)
	setTvNumber(lotto[3], binding.tvLotto4)
	setTvNumber(lotto[4], binding.tvLotto5)
	setTvNumber(lotto[5], binding.tvLotto6)
}
  ```
  
  ```kotlin
//로또 번호를 중복을 허용하지 않고 생성하는 함수
private fun getLottoNumber2() {
		val rnd = Random()
		val lotto = IntArray(6)
		while (true) {
			var isSame = false
			for (i in lotto.indices) {
				lotto[i] = rnd.nextInt(45) + 1
			}
			for (i in lotto.indices) {
				for (j in lotto.indices) {![Screenshot_20220721_153901](https://user-images.githubusercontent.com/88234731/180146698-cec89bef-e6ff-4933-868a-1875c3030492.png)

					if (i != j) {
						if (lotto[i] == lotto[j]) {
							isSame = true
						}
					}
				}
			}
			if (!isSame) {
				break
			}
		}
		lotto.sort()
		setTvNumber(lotto[0], binding.tvLotto1)
		setTvNumber(lotto[1], binding.tvLotto2)
		setTvNumber(lotto[2], binding.tvLotto3)
		setTvNumber(lotto[3], binding.tvLotto4)
		setTvNumber(lotto[4], binding.tvLotto5)
		setTvNumber(lotto[5], binding.tvLotto6)
}
  ```
