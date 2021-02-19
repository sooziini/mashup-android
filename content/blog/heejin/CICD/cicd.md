---

title: "CI / CD"

date: "2021-01-18"

tags: ["huijiny", "mash-up", "ci", "cd"]

description: "CI/CD에 대해서 알아보자!"

cover: "./희진.png"

---


안녕하세요! 10기 유희진입니다!

이번에 프로젝트를 진행하는 도중 팀장님께서 'ci 적용해놨으니 머지하기전에 ci test 다 돌고 success하면 머지해주세요' 라고 하셨습니다. ~~저는 못알아들었고..~~

그래서 ci에 대해서 공부한 내용을 적어보려고 합니다. 



## Background

소프트웨어가 거대해지고 복잡해지면서 팀 단위로 개발하게 되었고, 그 과정에서 분업과 협업은 필수가 되었습니다. 이 과정에서 Merge 과정은 까다롭고 테스트하는데 큰 자원을 소비하게 됩니다. 이 문제를 해결하기 위해 도입되었습니다.

개발 브랜치가 일정 기간 이상 이용되면, 통합의 어려움은 커지고 충돌 해결에 들어가는 시간이 길어지고 오류 발생 위험이 커집니다. 이를 극복하고자 변동 내용의 반영 빈도를 늘리는 자동화가 등장합니다.

빌드와 기능성을 검증하는 새로운 방법을 확보하고 기능의 개발과 배치 속도를 큰 폭으로 개선하기 시작하였습니다.





## Continuous Integration

지속적 통합, `continuous Integration`은 코드를 더 빈번하게 통합하고 소프트웨어 빌드 과정을 자동화하는 개발 접근법입니다. `지속적으로 퀄리티 컨트롤을 적용하는 프로세스를 실행하는 것이다` 라는 설명도 있더라구요.  

구현하기 위해선 다음과 같은 과정이 필요할 수 있습니다. 

### To Do

1. **git checkt**: 매일 깃 레포지토리의 코드를 확인하고 더 쉽게 프로덕션 단계로 이동시킬 수 있도록 점진적인 코드 변경에 중점을 둡니다.

2. **continuous testing**: 중요 테스트 가운데 일부를 자동화하고, 모든 빌드가 이런 테스트를 통과하도록 만듭니다. 다시말해, 지속적인 테스트가 지속적인 통합의 일부가 되도록 만듭니다.

3. **automated build**:  빌드 과정을 자동화 해 모든 소프트웨어 구성요소를 포함시키고, 개발 브랜치에 새 코드가 병합될 때 빌드를 진행합니다. 

   

이는 언제든 최신 Build를 고객에게 바로 제공 가능하게 합니다. 그리고 다수의 개발자가 동시에 개발관련 코드작업을 할 경우, 서로 충돌할 수 있는 문제를 해결하기 위함입니다.



## Continuous Delivery & Continuous Deployment

더 자주, 더 빨리 코드를 릴리즈하기 위한 다음 방법은 conticuous delivery & deployment 에 투자하는 것입니다.

지속적 배포는 자동으로 개발 및 테스트, production environment에 코드 변경사항을 적용하고 새 코드로 application을 구동하는데 필요한 단계들을 실행합니다. 개발자들이 적용한 변경사항이 버그 테스트를 거쳐 리포지토리에 자동으로 업로드 되는것이죠.

지속적 배포를 위해서는 더 많은 부분을 자동화할 수 있도록 일부 환경 설정을 변경해야만 합니다. 예를 들어, 모든 데이터베이스 연결과 API 엔드포인트, 사용자 이름, 암포, 기타 파라미터들을 환경 변수로 설정하고 대상환경에 맞춰 암호화하고 값을 할당해야합니다. 또한 도커나 쿠버네티스 같은 컨테이너 기술을 사용해 애플리케이션과 디펜던시들을 패키징해야한다고 합니다.

그런 후 성능 및 보안 테스트를 포함하는 자동화된 테스트를 구현합니다. 이 테스트는 배포 프로세서 내에서 실행할 수 있습니다.



## And ?

그런 후 모든 배포 단계를 자동화시키는데, 배포가 실패하는 경우를 위한 롤백 단계도 있어야 합니다. 이 모든 과정의 결과물을 `CI/CD 파이프라인`이라고 합니다. `CI/CD 파이프라인`을 확립한 후에는 기대하는 배포가 이루어지도록 만들어야 합니다. 이를 위해 결함 비율과 재개 비율같은 코드 품질 측정 기준을 모니터링 해야합니다. 자동화된 인프라와 배치의 많은 부분을 자동화하고 더 표준화된 아키텍처에 구축하면, 운영 엔지니어들이 애플리케이션 성능 향상과 보안 위험 해결에 더 많은 시간을 집중할 수 있습니다. 

지속적 통합과 지속적 테스트, 지속적 개발을 도입하면 팀은 장기적으로 새로운 기능을 개발하는 한 편, 매일매일의 배포 일정에서 작은 개선에 우선순위를 둘 수 있을 것입니다.



## So what's CI/CD?

- 지속적인 통합, 지속적인 서비스 제공, 지속적인 배포를 가능케 합니다.
- 새로운 코드 통합으로 인해 개발 및 운영팀에 발생하는 문제를 해결하는 솔루션 입니다.
- 애플리케이션 개발 단계를 자동화하여 애플리케이션을 보다 짧은 주기로 고객에게 제공하는 방법입니다.



![Image for post](https://miro.medium.com/max/625/1*4UtNE2uAl37bl_FmIafl6A.png)



## Reference

https://www.youtube.com/watch?v=tZtc6PDb8-c

https://ehddnjs8989.medium.com/circle-ci-62a498c9d438

https://www.youtube.com/watch?v=N9KbmHhesmE

https://hoi5088.medium.com/ci-cd-%EA%B0%9C%EB%85%90-4e6a45dbcfe2