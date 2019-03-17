# eosjs 사용하여 간단한 예제 만들어보기

eosjs를 통해서 랜덤키 한쌍을 생성하고 eoseouldotio 계정의 모니터링 하다가 (30분에 한번씩 동작하게 만들기)

contract에 claimreewards 액션이 발생하면 block_time, block_id, trx_id를 문자열로 ":" 을 기준으로 concat하여

서명 후 publicKey와 함께 행아웃 채팅으로 보내야합니다.

## 남은 과제
1. 행아웃 채팅으로 보내주기
2. ~~30분에 한번씩 발생하기~~ => 처음 한번 실행해준다음에 돌리고 싶다.

## 어려웠던 점

1. eosjs를 사용하여 계정의 정보를 가져오는 부분이 친절하지 않아서 구현에 애먹었었다. parameter문제였는데 data에다 계정의 정보를 추가하니 불러올수 있었다. 
2. 불러온 actions를 단순히 JSON.stringfy하니 전체가 문자열이 되어서 접근할 수가 없었다. 다시한번 JSON.parse()로 객체로 만들어서 접근하니 내마음대로 다룰 수가 있었다.
3. 이전의 상태와 비교를 해서 claimrewards가 연속 두번 발생하였을 때의 경우도 생각을 하였는데 이전의 상태와 비교하는 방법을 택하였다.
4. github issue