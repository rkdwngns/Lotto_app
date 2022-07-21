# Lotto_app

# 안드로이드 스튜디오를 사용하여 만든 로또 번호 생성기

<img width="165" alt="image" src="https://user-images.githubusercontent.com/93520535/180142855-bfded565-fe8f-48b7-bf4a-74ea353920a6.png">

로또 번호 생성기 실행 화면

```kotlin
  로또 번호의 중복을 허용하고 생성하는 함수
  
	private fun getLottoNumber1() {
		val rnd = Random()
		val lotto = IntArray(6)
//		for(i in 0 until 6) {
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
  중복을 허용하지 않는 함수
  
private fun getLottoNumber2() {
		val rnd = Random()
		val lotto = IntArray(6)
		while (true) {
			var isSame = false
			for (i in lotto.indices) {
				lotto[i] = rnd.nextInt(45) + 1
			}
			for (i in lotto.indices) {
				for (j in lotto.indices) {
					if (i != j) {
						if (lotto[i] == lotto[j]) {
							isSame = true
						}
					}
				}
			}
//			if( isSame == false) {
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





