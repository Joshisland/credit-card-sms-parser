# **[DEPRECATED]** credit-card-sms-parser
> 본 저장소는 더이상 업데이트되지 않습니다. Pull Request 및 Issue를 보내셔도 반영되지 않습니다.
[![Gem Version](https://badge.fury.io/rb/credit-card-sms-parser.svg)](http://badge.fury.io/rb/credit-card-sms-parser)

신용카드 회사에서 보내주는 sms 문자열을 읽어서 `상호명`, `사용금액`, `누적사용금액` 정보들을 추출해줍니다.

## 사용방법
```
$ gem install credit-card-sms-parser
$ pry
[1] pry(main)> require 'credit_card_sms_parser'
=> true
[2] pry(main)> include CreditCardSmsParser
=> Object
[3] pry(main)> parse_sms('하나(6*8*)***님 04/06 15:26 씨유판교 일시불/3,500원/누적-4,645원')
=> {:card=>"하나(6*8*)",
 :user_name=>"***님",
 :space=>" ",
 :date=>"04/06",
 :time=>"15:26",
 :shop_name=>"씨유판교",
 :type=>nil,
 :punctuation=>"/",
 :money=>3500,
 :money_total=>4645,
 :EOS=>nil}
```
어느 정도 수준으로 동작하는지 확인만 해보고 싶은 용도라면 아래 웹사이트에서 간편하게 확인해볼 수 있다:  
http://valider.realprobe.com/#/sms

## 현재까지 지원하는(걸로 추정되는) 카드사
* 현대카드
* 하나SK카드
* KEB 하나카드
* 국민카드
* 국민체크카드
* 농협
* 삼성법인카드
* 신한카드

## 프로젝트에 기여하기
파싱이 제대로 되지 않는 SMS 문자열을 Issue 에 올려주시거나 test 코드에 추가해주시면 반영해드립니다.
물론 lexer 에 들어있는 Rule 을 직접 고쳐서 수정해주시는 것도 환영합니다.
바로 위 항목의 `지원하는 걸로 추정하는 카드사`에 대한 정보도 새로운 것이나 변경할 사항이 있으시면 바로잡아주시길 부탁드립니다. 
