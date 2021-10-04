# Part 2 프로세스 관리

## Chapter 4 CPU 스케줄링

### 연습문제

1. 시스템 내 전체 프로세스의 수를 조절하는 것으로, 장기 스케줄링 또는 작업 스케줄링이라 불리는 스케줄링 수준은 무엇인가?
    - 고수준 스케줄링
2. 어떤 프로세스에 CPU를 할당하고 어떤 프로세스를 대기 상태로 보낼지 등을 결정하는 스케줄링 수준은 무엇인가?
    - 저수준 스케줄링
3. 어떤 프로세스가 CPU를 할당받아 실행 중이더라도 운영체제가 CPU를 강제로 빼앗을 수 있는 스케줄링은 무엇인가?
    - 선점형 스케줄링
4. 현재 입출력을 진행하는 프로세스로, 사용자와 상호작영이 가능하여 상호작용 프로세스라고도 불리는 것은 무엇인가?
    - 대화형 프로세스
5. 준비 큐에 도착한 순서대로 CPU를 할당하는 비선점형 스케줄링 알고리즘은 무엇인가?
    - FCFS 스케줄링
6. 준비 큐에 있는 프로세스 중 실행 시간이 가장 짧은 작업부터 CPU를 할당하는 비선점형 스케줄링 알고리즘은 무엇인가?
    - SJF 스케줄링
7. SJF 스케줄링 알고리즘의 단점으로 크기가 큰 작업이 계속 뒤로 밀리는 현상을 무엇이라고 하는가?
    - starvation. 아사 현상
8. 아사 현상을 해결하는 방법을 설명하시오.
    - aging. 프로세스가 양보할 수 있는 상한선을 정하는 것이다. 즉 프로세스가 자신의 순서를 양보할 때마다 나이를 한 살씩 먹어 최대 몇 살까지 양보하도록 규정하는 것이다.
9. 서비스를 받기 위해 대기한 시간과 CPU 사용 시간을 고려하여 우선순위를 정하는 스케줄링 알고리즘은 무엇인가?
    - HRN (Highest Response Ratio Next) 알고리즘. 최고 응답률 우선 알고리즘
10. 프로세스가 할당받은 시간(타임 슬라이스) 동안 작업하다가 작업을 완료하지 못하면 준비 큐의 맨 뒤로 가서 다음 자기 차례가 올 때까지 기다리는 선점형 스케줄링 알고리즘 중 가장 단순한 것은 무엇인가?
    - Round Robin 알고리즘
11. 타임 슬라이스의 크기와 문맥 교환의 관계를 설명하시오.
    - 타임 슬라이스가 너무 크면 하나의 작업이 끝난 뒤 다음 작업이 시작되는 것처럼 보인다. 프로그램이 동시에 실행되지 않는 것처럼 보여 불편함을 초래한다.
    - 타임 슬라이스가 작은 경우, 사용자는 여러 프로그램이 동시에 실행되는 것처럼 느낄 것이다. 그러나 문맥 교환이 너무 자주 일어나 문맥 교환에 걸리는 시간이 실제 작업 시간보다 상대적으로 커지며, 문맥 교환에 많은 시간을 낭비하여 실제 작업을 못하는 문제가 생긴다.
12. 기본적으로 라운드 로빈 방식을 사용하지만, CPU를 할당받을 프로세스를 선택할 때 남아 있는 작업 시간이 가장 적은 것을 선택하는 스케줄링 알고리즘은 무엇인가?
    - SRT (Shortest Remaining Time) 스케줄링
13. 우선순위에 따라 준비 큐를 여러 개 사용하며 고정형 우선순위를 적용하는 스케줄링 알고리즘은 무엇인가?
    - 다단계 큐 스케줄링
14. 우선순위에 따라 준비 큐를 여러개 사용하며, 프로세스가 CPU를 사용한 후 우선순위가 낮아지는 특징을 가진 스케줄링 알고리즘은 무엇인가?
    - 다단계 피드백 큐 스케줄링
15. 다단계 피드백 큐 스케줄링에서 마지막 큐에 있는 프로세스(우선순위가 가장 낮은 프로세스)의 타임 슬라이스 크기는 얼마인가?
    - 무한대 (FCFS 스케줄링 방식으로 동작)
16. 다단계 피드백 큐 스케줄링에서 우선순위가 낮아질수록 타임 슬라이스의 크기는 어떻게 변하는가?
    - 다단계 피드백 큐 스케줄링은 우선순위가 낮은 프로세스의 실행 기회를 확대하려고 하지만, 그렇다고 해도 우선순위가 낮은 프로세스가 우선순위가 높은 프로세스보다 CPU를 얻을 확률이 여전히 낮다. 따라서 어렵게 얻은 CPU를 좀 더 오랫동안 사용할 수 있도록 우선순위가 낮은 큐의 타임 슬라이스를 크게 설정한다.
17. 다단계 피드백 큐 스케줄링에서 마지막 큐(우선순위가 가장 낮은 큐)는 어떤 스케줄링 알고리즘처럼 동작하는가?
    - FCFS 스케줄링