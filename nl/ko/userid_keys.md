---

copyright:

  years: 2015, 2017
lastupdated: "2017-10-03"

---

{:shortdesc: .shortdesc}
{:codeblock: .codeblock}
{:screen: .screen}
{:new_window: target="_blank"}

# 사용자 API 키 관리
{: #userapikey}

연합 또는 비연합 사용자는 CLI에서 사용하거나 사용자 ID처럼 로그인하기 위한 자동화의 일부로 사용하도록 API 키를 작성할 수 있습니다. {{site.data.keyword.Bluemix_notm}} UI 또는 {{site.data.keyword.Bluemix_notm}} CLI를 사용하여 키 나열, 키 작성, 키 업데이트 또는 키 삭제로 API 키를 관리할 수 있습니다. 사용자 ID와 연관된 {{site.data.keyword.Bluemix_notm}} API 키를 관리하려면 **관리** &gt; **보안** &gt; **Bluemix API 키**로 이동하여 설명 및 날짜가 있는 API 키 목록을 확인하십시오. 그러면 이 페이지에서 API 키를 작성, 편집 또는 삭제할 수 있습니다. 사용 가능한 CLI 명령의 전체 목록은 [API 키 및 정책 관리를 위한 명령](/docs/cli/reference/bluemix_cli/bx_cli.html#bx_commands_iam)을 참조하십시오.

[연합 사용자](/docs/admin/adminpublic.html#federatedid)로서, `BLUEMIX_API_KEY` 환경 변수를 사용하여 로그인하는 데 API 키를 사용할 수 있습니다. API 키를 사용한 로그인에 대한 자세한 정보는 [{{site.data.keyword.Bluemix_notm}} CLI `bluemix login` 명령](/docs/cli/reference/bluemix_cli/bx_cli.html#bluemix_login) 및 [cf CLI `cf login` 명령](/docs/cli/reference/cfcommands/index.html#cf_login) 문서를 참조하십시오. 

## API 키 작성

{{site.data.keyword.Bluemix_notm}} 사용자는 스크립트에 비밀번호를 제공하지 않고 API 키를 사용하여 프로그램 또는 스크립트를 사용할 수 있습니다. API 키를 사용하면 사용자나 조직이 다양한 프로그램에 대해 여러 API 키를 작성할 수 있으며, 문제가 발생할 경우 다른 API 또는 사용자에게 영향을 주지 않고 개별적으로 API 키를 삭제할 수 있습니다. 

UI에서 사용자 ID의 API 키를 작성하려면 다음을 수행하십시오.

1. **관리** &gt; **보안** &gt; **Bluemix API 키**로 이동하십시오. 
2. **API 키 작성**을 클릭하십시오. 
3. API 키의 이름과 설명을 입력하십시오.
4. **API 키 작성**을 클릭하십시오. 
5. 그리고 **표시**를 클릭하여 나중에 복사하고 저장할 수 있도록 API 키를 표시하거나 **API 키 다운로드**를 클릭하십시오. 

**참고**: 보안상 이유로 API 키는 작성 시에만 복사하거나 다운로드할 수 있습니다. API 키를 유실한 경우에는 새 API 키를 작성해야 합니다. 

CLI를 사용하여 API 키를 작성하려면 다음을 수행하십시오. 

1. `bluemix iam api-key-create NAME [-d DESCRIPTION] [-f, --file FILE]`을 명령 프롬프트에 입력하고 이름, 설명 및 키를 저장하기 위한 파일을 지정하십시오. 예:

```
bluemix iam api-key-create MyKey -d "this is my API key" -f key_file
``` 

CLI를 사용하여 API 키가 작성된 후에 다음과 같이 bx CLI와 함께 키를 사용할 수 있는 몇 가지 방법이 있습니다. 

* `bx login` 명령과 함께 입력
```
 bx login --apikey <your api key>
```
* `bx login` 명령과 함께 사용하기 위한 API 키 파일 작성: 
 ```
 bx login --apkey @apikeyfile
 ```
 `apikeyfile`은 `bx iam api-key-create` 명령에서 `—file` 옵션을 사용하여 작성됩니다.
* 명령 프롬프트에서 `BLUEMIX_API_KEY=<your api key>`를 입력한 다음에 `bx login`을 입력하여 환경 변수를 설정할 수 있습니다.
* 또는 bx CLI를 피하고 API 키를 사용하여 단지 cf CLI에 로그인하려는 경우에는 다음을 입력하십시오. 
 ```
 cf login -u apikey -p <yourapikey>
 ```
  이 옵션에서 `apikey`의 사용자 이름을 사용하고 비밀번호는 `apikey`입니다. 이제 `apikey`를 Eclipse와 같은 다른 도구 또는 사용자 이름과 비밀번호만 허용하는 `cf login`을 찾는 다른 위치에서 사용할 수 있습니다.

## API 키 업데이트

API 키의 설명 또는 이름을 변경하려는 경우, UI 또는 CLI에서 다음 단계를 완료하십시오.

API 키를 편집하려면 다음을 수행하십시오. 

1. **관리** &gt; **보안** &gt; **Bluemix API 키**로 이동하십시오. 
2. 테이블에 나열된 API 키의 **조치** 메뉴에서 **이름 및 설명 편집**을 클릭하십시오.  
3. API 키에 대한 정보를 업데이트하십시오.
4. **API 키 업데이트**를 클릭하십시오. 

CLI를 사용하여 API 키를 편집하려면 다음을 수행하십시오. 

1. 명령 프롬프트에 `bluemix iam api-key-update NAME [-n NAME] [-d DESCRIPTION]`을 입력하여 키에 대한 이전 이름, 새 이름 및 새 설명을 지정하십시오. 예:

```
bluemix iam api-key-update MyCurrentName -n MyNewName -d "the new description of my key"
```

## API 키 삭제

키 회전 전략을 사용하는 경우, 이전 키를 삭제하고 새 키로 바꾸려고 할 수 있습니다. 

API 키를 삭제하려면 다음을 수행하십시오.  

1. **관리** &gt; **보안** &gt; **Bluemix API 키**로 이동하십시오. 
2. 테이블에 나열된 API 키의 **조치** 메뉴에서 **삭제**를 클릭하십시오. 
3. 그리고 **키 삭제**를 클릭하여 삭제를 확인하십시오. 

CLI를 사용하여 API 키를 삭제하려면 다음을 수행하십시오. 
1. 명령 프롬프트에 `bluemix iam api-key-delete NAME`을 입력하여 삭제해야 하는 키의 이름을 지정하십시오. 
