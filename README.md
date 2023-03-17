# Lambda Zombi

An lambda invoke is always executed in an execution 

## init

`yarn deploy`
`yarn watch`

## execute examples

1. `aws lambda invoke --function-name zombi --cli-binary-format raw-in-base64-out --payload file://examples/errorEx.json res`
2. `aws lambda invoke --function-name zombi --cli-binary-format raw-in-base64-out --payload file://nextEx.json res` 

## Result

```
[/aws/lambda/zombi] 2:09:29 PM INIT_START Runtime Version: nodejs:14.v29        Runtime Version ARN: arn:aws:lambda:eu-central-1::runtime:be6b7a67cb4533b2e602f284c4e41058155b081b5879c71929b33e71c124b81d
[/aws/lambda/zombi] 2:09:29 PM START RequestId: c6988688-6c8e-40bc-9414-9421679b55ef Version: $LATEST
[/aws/lambda/zombi] 2:09:29 PM 2023-03-17T13:09:29.304Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    before 'kaput'
[/aws/lambda/zombi] 2:09:29 PM 2023-03-17T13:09:29.305Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    before 'Wo ist er hin?'
[/aws/lambda/zombi] 2:09:29 PM 2023-03-17T13:09:29.305Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    before 'geht durch'
[/aws/lambda/zombi] 2:09:29 PM 2023-03-17T13:09:29.505Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    'geht durch' done
[/aws/lambda/zombi] 2:09:29 PM 2023-03-17T13:09:29.805Z c6988688-6c8e-40bc-9414-9421679b55ef    ERROR   Invoke Error    {"errorType":"Error","errorMessage":"zombi","stack":["Error: zombi","    at zombieFunc (/var/task/index.js:33:11)","    at async Promise.all (index 0)","    at async Runtime.handler (/var/task/index.js:39:15)"]}
[/aws/lambda/zombi] 2:09:29 PM END RequestId: c6988688-6c8e-40bc-9414-9421679b55ef
[/aws/lambda/zombi] 2:09:29 PM REPORT RequestId: c6988688-6c8e-40bc-9414-9421679b55ef   Duration: 506.11 ms     Billed Duration: 507 ms Memory Size: 128 MB     Max Memory Used: 57 MB  Init Duration: 163.92 ms
[/aws/lambda/zombi] 2:10:51 PM START RequestId: c03b4b5b-f80b-45ab-b9d1-b67033a2ec34 Version: $LATEST
[/aws/lambda/zombi] 2:10:51 PM 2023-03-17T13:10:51.758Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    'Wo ist er hin?' done
[/aws/lambda/zombi] 2:10:51 PM 2023-03-17T13:10:51.807Z c03b4b5b-f80b-45ab-b9d1-b67033a2ec34    INFO    before 'Neu 1'
[/aws/lambda/zombi] 2:10:51 PM 2023-03-17T13:10:51.807Z c03b4b5b-f80b-45ab-b9d1-b67033a2ec34    INFO    before 'Neu lahm'
[/aws/lambda/zombi] 2:10:52 PM 2023-03-17T13:10:52.428Z c03b4b5b-f80b-45ab-b9d1-b67033a2ec34    INFO    'Neu lahm' done
[/aws/lambda/zombi] 2:10:53 PM 2023-03-17T13:10:53.308Z c03b4b5b-f80b-45ab-b9d1-b67033a2ec34    INFO    'Neu 1' done
[/aws/lambda/zombi] 2:10:53 PM 2023-03-17T13:10:53.310Z c03b4b5b-f80b-45ab-b9d1-b67033a2ec34    INFO    [ undefined, undefined ]
[/aws/lambda/zombi] 2:10:53 PM END RequestId: c03b4b5b-f80b-45ab-b9d1-b67033a2ec34
[/aws/lambda/zombi] 2:10:53 PM REPORT RequestId: c03b4b5b-f80b-45ab-b9d1-b67033a2ec34   Duration: 1570.14 ms    Billed Duration: 1571 ms        Memory Size: 128 MB     Max Memory Used: 58 MB
```

The scary|interessing part is this: 

``` 
[/aws/lambda/zombi] 2:10:51 PM 2023-03-17T13:10:51.758Z c6988688-6c8e-40bc-9414-9421679b55ef    INFO    'Wo ist er hin?' done
```
