## 리프레시 토큰 (Refresh Token)

엑세스 토큰(access token)이 만료되었을 때, 새로운 엑세스 토큰을 발급받기 위해 사용하는 토큰. 일반적으로 엑세스 토큰은 짧은 유효 기간을 가지며, 리프레시 토큰은 더 긴 유효 기간을 가진다.

기능

- 엑세스 토큰 재발급: 엑세스 토큰이 만료되면, 리프레시 토큰을 이용해 새로운 엑세스 토큰을 발급
- 보안 강화: 짧은 유효 기간을 가진 엑세스 토큰을 사용함으로써, 엑세스 토큰이 탈취되었을 때의 피해를 줄일 수 있음

  
장점

- 짧은 유효 기간의 엑세스 토큰 사용으로 인해, 탈취된 토큰의 유효성을 최소화할 수 있음 (보안 강화)
- 사용자가 자주 로그인하지 않아도 되어 편리

  
단점
- 리프레시 토큰을 관리해야 하므로 구현이 복잡
- 리프레시 토큰을 저장하고 관리하기 위한 추가 저장소가 필요

  
## 블랙리스트 (Token Blacklist)

특정 토큰을 무효화하기 위해 사용하는 목록. 블랙리스트에 등록된 토큰은 더 이상 유효하지 않으며, 인증에 사용될 수 없다

기능

- 토큰 무효화: 블랙리스트에 추가된 토큰은 더 이상 사용할 수 없게 됨
- 보안 관리: 특정 토큰을 무효화하여 보안을 강화할 수 있다

  
장점

- 보안 강화: 유효하지 않은 토큰을 무효화하여 보안 사고를 예방
- 필요에 따라 특정 토큰만 무효화할 수 있다


단점

- 블랙리스트를 저장하기 위한 저장소가 필요
- 블랙리스트 조회 과정에서 성능이 저하 우려

  
## Access Log
애플리케이션에 대한 모든 접근을 기록하는 기능. 이는 사용자가 애플리케이션에 접근한 기록을 저장한다.

기능

- 접속 기록 저장: 누가, 언제, 어디서, 어떤 경로로 애플리케이션에 접근했는지 기록
- 보안 분석: 비정상적인 접근 패턴을 탐지하여 보안 사고를 예방
- 접속 로그를 통해 사용자 활동을 추적하고 감사


장점

- 보안 강화: 비정상적인 활동을 모니터링하고 대응할 수 있다
- 감사 가능성: 사용자 활동을 추적하여 문제가 발생했을 때 원인을 분석할 수 있다

단점

- 로그 데이터를 저장하기 위한 공간 필요
- 로그 기록 과정에서 성능이 저하될 수 있다


## JWT (JWT Authenticatio)

JWT (JSON Web Token)는 사용자 인증 정보를 JSON 형식으로 인코딩한 토큰. JWT는 보안이 필요한 정보 교환에 사용된다. 

기능

- 인증 및 인가: 사용자 인증 정보를 포함하여 인증 및 인가에 사용
- 정보 교환: 서버 간에 안전하게 정보를 교환할 수 있다
- 무상태성 유지: 서버는 클라이언트 상태를 유지하지 않아도 되며, 클라이언트가 필요한 모든 정보를 JWT에 담아 전달


장점

- 서버는 클라이언트의 상태를 유지하지 않기 때문에 확장성이 높다.
- 보안: 서명된 토큰을 사용하여 데이터의 무결성을 보장
- JSON 형식으로 인코딩되어 있어 파싱이 쉽다

단점

- JWT의 크기가 커질 수 있으며, 이는 네트워크 트래픽을 증가시킬 수 있음
- 보안 위험: 토큰이 탈취되면, 탈취된 토큰을 사용하여 불법적인 접근이 가능 이를 방지하기 위해 짧은 유효 기간을 설정하거나, 리프레시 토큰을 사용
  
## 도커 (Docker)
컨테이너화 기술을 통해 애플리케이션을 격리된 환경에서 실행할 수 있게 하는 플랫폼. 컨테이너는 필요한 모든 것을 포함한 독립적인 실행 환경을 제공

기능

- 컨테이너화: 애플리케이션을 컨테이너에 담아 어디서나 동일하게 실행할 수 있음
- 이미지 관리: 도커 이미지를 통해 애플리케이션의 상태를 저장하고 배포할 수 있다
- 네트워킹: 컨테이너 간 네트워킹을 지원하여 복잡한 애플리케이션을 구성할 수 있다
- 오케스트레이션: 도커 스웜, 쿠버네티스 등의 도구를 통해 여러 컨테이너를 관리할 수 있다

장점

- 어디서나 동일하게 실행할 수 있는 환경을 제공하여 개발 및 배포의 일관성을 유지할 수 있음
- 각 컨테이너는 독립적으로 실행되어 다른 컨테이너와 격리
- 자원 효율성: 가상 머신보다 가볍고 빠르며, 시스템 자원을 효율적으로 사용할 수 있다

단점

- 컨테이너 오케스트레이션 및 관리가 복잡할 수 있다
- 보안 문제: 컨테이너 격리가 완벽하지 않으며, 잘못된 설정으로 인해 보안 문제가 발생할 수 있다
- 테이너화된 애플리케이션의 디버깅이 어려움
