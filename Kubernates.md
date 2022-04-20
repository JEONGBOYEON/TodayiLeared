## Kubernates pod 구성 패턴

1. Sidecar 패턴
- 원래 사용하려고 했던 기본 컨테이너의 **기능을 확장하거나 강화** 하려는 용도로 사용
- 기본 컨테이너는 원래의 목적에 충실, 사이드카 컨테이너는 부가적인 기능을 담당
- ex) 기본 컨테이너: 웹서버 / 사이드카 컨테이너: 로그 수집
- 재사용성이 높아짐(다른 기본 컨테이너로 변경 가능)

2. Ambassador 패턴
- 파드내에 프록시 역할을 하는 컨테이너를 추가하는 패턴
- 파드에서 외부로 접근할때, 프록시에서 연결하도록 함
- 기본 컨테이너 -> locathost -> 프록시 컨테이너 -> 외부
- 트랙픽을 보다 세밀하게 제어 가능
- ex) service mesh용 오픈소스 istio

3. Adapter 패턴
- 파드 외부로 노출되는 정보를 표준화하는 역할
- ex) 모니터링 지표를 표준화된 형식으로 모니터링 시스템에 보냄

