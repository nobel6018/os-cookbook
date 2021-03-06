# Part 2 프로세스 관리

## Chapter 5 프로세스 동기화

### 연습문제

1. 프로세스 간 통신에서 데이터를 양방향으로 전송 가능하지만 동시 전송은 불가능하고 특정 시점에 한쪽 방향으로만 전송할 수 있는 통신 방식은 무엇인가?
    - 반양방향 통신
2. 상태 변화를 살펴보기 위해 반복문을 무한 실행하며 기다리는 것을 무엇이라 하는가?
    - 바쁜 대기(busy waiting)
3. 프로세스 간 통신에서 대기가 없는 통신과 대기가 있는 통신의 예를 각각 제시하시오.
    - 대기가 없는 통신(비동기화 통신): 전역 변수, 파일
    - 대기가 있는 통신(동기화 통신): 파이프, 소켓
4. 파이프를 이용하여 통신할 때 파이프를 2개 사용하는 이유는 무엇인가?
    - 파이프는 단방향 통신이다. 이를 극복하여 파이프를 2개 사용하여 양방향으로 통신하기 위해서
5. 공유 자원을 병행적으로 읽거나 쓰는 상황을 무엇이라 하는가?
    - 경쟁 조건 (race condition)
6. 공유 자원의 접근 순서에 따라 실행 결과가 달라지는 프로그램의 영역은 무엇인가?
    - 임계구역
7. 임계구역 해결 조건 중 한 프로세스가 임계구역에 들어갔을 때 다른 프로세스는 임계구역에 들어갈 수 없는 조건을 무엇이라 하는가?
    - 상호 배제
8. 임계구역 해결 조건 중 한 프로세스가 다른 프로세스의 진행을 방해해서는 안 된다는 조건을 무엇이라 하는가?
    - 진행의 융통성
9. 임계구역 문제를 하드웨어적으로 해결한 방식으로, 하드웨어의 지원을 받아 명령어를 실행하는 도중에 타임아웃이 걸리지 않도록 하는 방식을 무엇이라 하는가?
    - 하드웨어적인 해결 방법. 검사와 지정 (test-and-set)
10. 세마포어의 Semaphore(n)에서 n은 무엇을 가리키는가?
    - 공유 가능한 자원의 수
11. 세마포어에서 내부 변수를 RS라고 할 때 세마포어 P()의 내부 코드를 쓰시오.
    ```c
    if RS > 0 then RS = RS - 1 
    else block()
    ```
12. 세마포어에서 내부 변수를 RS라고 할 때 세마포어 V()의 내부 코드를 쓰시오.
    ```c
    RS = RS + 1
    wake_up()
    ```
13. 세마포어가 제대로 작동하지 않는 경우를 설명하시오.
    - 세마포어를 사용하지 않고 임계구역에 들어간 경우
    - P()를 두 번 사용하여 wake_up 신호가 발생하지 않은 경우. 세마포어 큐에 대기하고 있는 프로세스가 무한 대기에 빠진다
    - P()와 V()를 반대로 사용하여 상호 배제가 보장되지 않은 경우
14. 세마포어의 내부 코드도 타임아웃이 걸리면 문제가 발생할 수도 있다. 그래서 내부 코드는 무엇으로 보호받는가?
    - 검사와 지정 (test-and-set)
15. 공유 자원을 내부적으로 숨기고 공유 자원에 접근하기 위한 인터페이스만 제공함으로써 자우너을 보호하고 프로세스 간에 동기화를 시키는 것으로, 세마포어의 단점을 해결하면서 임계구역 문제를 해결한 방시은 무엇인가?
    - 모니터
