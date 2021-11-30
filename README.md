# ROBO77
manipulated robo77 with C

전자공학도를위한프로그래밍기초 _프로젝트1

※오리지널 로보77 카드게임 규칙 참고 동영상: https://youtu.be/Hcq3aFwpm5E

※로보77 문제 정의:
  1. 전체 카드를 섞어서 뒤집힌 상태의 카드묶음 생성
  2. 게임 시작 시 각 플레이어 별로 N_CARDHOLD 개의 카드를 flipped card group로부터 순서대로 받음
  3. 플레이어 0부터 자기 턴을 진행하며, 각 턴에서 플레이어는 가지고 있는 카드에서 1장의 카드를 바닥에 놓음
  4. 바닥에 놓은 카드(opend card group)가 x2 카드가 아닌 경우, 카드의 숫자와 지금까지 누적된 카드 숫자 합을 더해서 현재 누적 숫자를 계산
        - 누적 숫자는 음수가 되지 않으며, 합 결과가 음수인 경우에는 누적 숫자를 0으로 설정
  5. 누적 숫자가 아래와 같은 경우는 현재 턴의 플레이어는 생명을 1개 잃게 되고, 누적 숫자 상태에 따라 현재 게임의 지속 여부 결정
        - 누적 숫자가 11의 배수인 경우 > 현재 게임 계속 진행
        - 누적 숫자가 77 이상인 경우 > 현재 게임 종료
  6. 바닥에 놓은 카드가 x2 카드인 경우, 누적 숫자는 그대로이며, 다음 턴의 플레이어는 2장의 카드를 내야 함
        - 2장의 카드는 현재 보유한 5장의 카드 중에서 하나씩 순차적으로 선택
        - 첫번째 선택 카드는 숫자 카드이어야 함 (x2 카드는 첫번쨰에 낼 수 없음)
  7. flipped card group이 소진되면 opend card group을 섞어서 flipped card group을 재생성
     (이떄 누적 숫자는 그대로임)
     
※카드 구성:
- 숫자 2~9 / 각 3장씩 총 24장
- 숫자 10 / 8장
- 숫자 11, 22, 33, 44, 55, 66, 76 / 각 1장씩 총 7장
- 숫자 0 / 4장
- 숫자 -10 / 4장
- x2 (double) / 4장
- reverse 카드는 없음
- ▷ 총 51장

※출력
- 현재 게임 회차
- 각 턴의 플레이어 번호 및 현재 누적 숫자
- 현재 턴에서 플레이어가 가진 카드
- 선택되어 바닥에 놓는 카드
- 생명을 잃은 경우 이에 대한 문구 및 원인
- 최종 결과 (생명을 모두 잃고 진 플레이어)
