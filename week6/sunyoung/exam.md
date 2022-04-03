# EC2 SAA Section 1, 6, 7

# Section 4: ****IAM 및 AWS CLI 퀴즈****

### 1)

> IAM 정책은 하나 이상의 문들로 구성됩니다. IAM 정책의 문들은 다음을 제외하고 구성됩니다:
> 

```
1. 효과
2. 원칙
3. 버전
4. 동작
5. 리소스
```

```
>> 정답 
3) 버전
```

번역이 오히려 너무 직관적으로 되어있어서 더 헷갈렸던 것 같다.

### 해설

IAM 정책의 문들은 Sid, Effect, Principal, Action, Resource 및 Condition으로 구성됩니다. 

버전은 문이 아니라 IAM 정책의 일부입니다.

[https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/reference_policies_elements.html](https://docs.aws.amazon.com/ko_kr/IAM/latest/UserGuide/reference_policies_elements.html)

### 2)

> IAM 사용자 그룹은 IAM 사용자와 기타 사용자 그룹을 포함할 수 있다.
> 

```
1. 참
2. 거짓
```

```
>> 정답 
2) 거짓
```

### 해설

IAM 사용자 그룹들에는 IAM 사용자들만 포함될 수 있습니다.

### 3)

> 다음 중 IAM 보안 도구는 무엇일까요?
> 

```
1. IAM 자격 증명 보고서
2. IAM Root Account Manager
3. IAM Services Report
4. IAM Security Advisor
```

```
>> 정답 
1) IAM 자격 증명 보고서
```

### 해설

IAM 자격 증명 보고서에는 모든 AWS 계정의 IAM 사용자와 자격 증명의 상태가 표시됩니다.

# Section 9: ****RDS, Aurora 및 ElastiCache 퀴즈****

### 4)

> 사용자가 연결할 때 암호를 입력하도록 하여 ElastiCache Redis 클러스터의 보안을 강화할 수 있는 방법은 무엇일까요?
> 

```
1. Redis 인증 사용
2. IAM 인증 사용
3. 보안 그룹
```

```
>> 정답 
1) Redis 인증 사용
```

### 해설

보안그룹 - 보안 그룹은 ElastiCache Redis 클러스터 인스턴스로 가는 트래픽을 필터링하는 데 도움이 되지만 애플리케이션 수준 인증에는 도움이 되지 않습니다.

IAM 인증 - 지원 X

### 5)

> 다음 중 RDS 읽기 전용 복제본과 다중 AZ의 복제에 대한 설명으로 옳지 않은 것은 무엇일까요?
> 

```
1. 읽기 전용 복제본은 비동기식 복제를 사용하고 다중 AZ는 비동기식 복제를 사용합니다.
2. 읽기 전용 복제본은 비동기식 복제를 사용하고 다중 AZ는 동기식 복제를 사용합니다.
3. 읽기 전용 복제본은 동기식 복제를 사용하고 다중 AZ는 동기식 복제를 사용합니다.
4. 읽기 전용 복제본은 동기식 복제를 사용하고 다중 AZ는 비동기식 복제를 사용합니다.
```

```
>> 정답 
2) 읽기 전용 복제본은 비동기식 복제를 사용하고 다중 AZ는 동기식 복제를 사용합니다.
```

### 해설

읽기 전용 복제본은 비동기식 복제를 사용하고 다중 AZ는 동기식 복제를 사용합니다.

### 6)

> RDS 데이터베이스의 경우 최대 .............개의 읽기 복제본을 가질 수 있습니다.
> 

```
1. 3
2. 5
3. 7
```

```
>> 정답 
2) 5
```

### 해설

RDS 데이터베이스의 경우 최대 5개의 읽기 복제본을 가질 수 있습니다.

(오로라는 15개)

# Section 10: ****Route 53****

### 7)

> 여러분은 새로운 Elastic Beanstalk 환경을 배포했으며 프로덕션 트래픽의 5%를 이 새로운 환경으로 보내려고 합니다. 이를 통해 CloudWatch 지표를 모니터링하고 새 환경에 버그가 없는지 확인할 수 있습니다. 어떤 Route 53 레코드 유형으로 그렇게 할 수 있을까요?
> 

```
1. 단순
2. 가중치
3. 대기 시간
4. 장애 조치
```

```
>> 정답 
2) 가중치
```

### 해설

가중치 기반 라우팅 정책을 사용하면 가중치(예: 백분율)를 기반으로 트래픽의 일부를 리디렉션할 수 있습니다. 트래픽의 일부를 애플리케이션의 새 버전으로 보내는 것은 일반적인 사용 사례입니다.

### 8)

> 새 Elastic Load Balancer를 가리키도록 Route 53 레코드의 myapp.mydomain.com 값을 업데이트했지만 사용자가 여전히 이전 ELB로 리디렉션되는 것 같습니다. 이 동작의 가능한 원인은 무엇일까요?
> 

```
1. Alias 레코드 때문에
2. CNAME 레코드 때문에
3. TTL 때문에
4. Route 53 상태 확인으로 인해
```

```
>> 정답 
3) TTL 때문에
```

### 해설

각 DNS 레코드에는 이러한 값을 캐시하고 DNS 요청으로 DNS 해석기에 과부하가 걸리지 않도록 클라이언트에게 명령하는 TTL(Time To Live)이 있습니다. TTL 값은 값을 캐시해야 하는 기간과 DNS 확인자로 가야 하는 요청 수 사이의 균형을 유지하도록 설정해야 합니다.

### 9)

> 여러분은 두 개의 서로 다른 AWS 리전 `us-west-1` 및 `eu-west-2`에서 호스팅되는 애플리케이션이 있습니다. 애플리케이션 서버에서 사용자에 대한 응답 시간을 최소화하여 사용자가 최상의 사용자 경험을 얻을 수 있기를 바랍니다. 어떤 Route 53 라우팅 정책을 선택해야 할까요?
> 

```
1. 다중 값
2. 가중치
3. 대기 시간
4. 지오로케이션
```

```
>> 정답 
3) 대기 시간
```

### 해설

지연 라우팅 정책은 사용자와 AWS 리전 간의 지연 시간을 평가하고 지연 시간(예: 응답 시간)을 최소화하는 DNS 응답을 받는 데 도움이 됩니다.