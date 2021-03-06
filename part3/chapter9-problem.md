# Part 3 메모리 관리

## Chapter 9 가상 메모리 관리

### 연습문제

1. 메모리 가져오기 정책 중, 사용자가 요구할 때 해당 페이지를 메모리로 가져오는 방식은 무엇인가?
    - 요구 페이징
2. 요구 페이징과 반대로 앞으로 필요할 것이라고 예상되는 페이지를 미리 가져오는 방식은 무엇인가?
    - 미리 가져오기
3. 페이지 테이블 엔트리의 구조 중, 페이지가 실제 메모리에 있는지 나타내는 비트는 무엇인가?
   - 유효 비트
4. 페이지 테이블 엔트리의 구조 중, 페이지가 메모리에 올라온 후 사용한 적이 있는지 알려주는 비트는 무엇인가?
   - 접근 비트
5. 페이지 테이블 엔트리의 구조 중, 페이지가 메모리에 올라온 후 데이터의 변경이 있는지 알려주는 비트는 무엇인가?
   - 변경 비트
6. 프로세스가 페이지를 요청했을 때 해당 페이지가 메모리에 없는 상황을 무엇이라 하는가?
   - 페이지 부재
7. 기억장치에 접근하는 패턴이 메모리 전체에 고루 분포되는 것이 아니라 특정 영역에 집중되어 있는 성질을 무엇이라 하는가?
   - 지역성
8. 처음으로 메모리에 올라온 페이지를 스왑 영역으로 보내는 페이지 교체 알고리즘은 무엇인가?
   - FIFO 페이지 교체 알고리즘
9. 미래의 접근 패턴을 기준으로 대상 페이지를 선정하여 스왑 영역으로 보내는 방식으로, 실제로 구현이 불가능한 페이지 교체 알고리즘은 무엇인가?
   - 최적 페이지 교체 알고리즘
10. 시간적으로 멀리 떨어진 페이지를 스왑 영역으로 보내는 페이지 교체 알고리즘은 무엇인가?
    - LRU(Least Recently Used) 페이지 교체 알고리즘
11. 사용 빈도가 적은 페이지를 스왑 영역으로 보내는 페이지 교체 알고리즘은 무엇인가?
    - LFU(Least Frequently Used) 페이지 교체 알고리즘
12. 최근에 사용한 적이 없는 페이지를 스왑 영역으로 보내는 페이지 교체 알고리즘은 무엇인가?
    - NUR(Not Used Recently) 페이지 교체 알고리즘
13. FIFO 변형 페이지 교체 알고리즘 중, 성공한 페이지를 큐의 맨 뒤로 옮김으로써 기회를 한 번 더 주는 페이지 교체 알고리즘은 무엇인가?
    - 2차 기회 페이지 교체 알고리즘
14. FIFO 변형 페이지 교체 알고리즘 중, 대상 페이지를 가리키는 포인터를 사용하여 포인터가 큐의 맨 바닥으로 내려가면 다음에 다시 큐의 처음을 가리키게 하는 페이지 교체 알고리즘은 무엇인가?
    - 시계 알고리즘
15. 하드디스크의 입출력이 많아져서 잦은 페이지 부재로 작업이 거의 멈춰버린 상태를 무엇이라 하는가?
    - 스레싱
16. 동적 프레임 할당 방식 중, 최근 일정 시간 동안 참조된 페이지를 집합으로 유지하고 이 집합에 있는 페이지들을 물리 메모리에 유지하는 것은 무엇인가?
    - 작업집합 모델 (Working Set Model)
17. 동적 프레임 할당 방식 중, 페이지 부재 비율의 상한선과 하한선을 설정하고 페이지 부재 비율이 상한선을 초과하면 할당 프레임을 늘려주는 것은 무엇인가?
    - 페이지 부재 빈도
