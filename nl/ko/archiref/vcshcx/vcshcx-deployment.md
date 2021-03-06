---

copyright:

  years:  2016, 2019

lastupdated: "2019-04-18"

subcollection: vmware-solutions


---

# 클라우드 및 클라이언트 배치
{: #vcshcx-deployment}

최소 HCX 설치는 단일 클라우드 및 클라우드 측 배치로 구성됩니다. 클라이언트와 클라우드 측 간에
네트워크 연결이 있다는 가정 하에 HCX 클라이언트 측은 HCX에서 지원하는
모든 버전의 vSphere에 설치할 수 있습니다.

## 요구사항
{: #vcshcx-deployment-req}

- HCX Manager – CPU 개수 4, 메모리 12G, 디스크 60G
- CGW – CPU 개수 8, 메모리 3G, 디스크 2G
- L2C – CPU 개수 8, 메모리 3G, 디스크 2G
- WAN Opt – CPU 개수 8, 메모리 14G, 디스크 100G

## 클라우드
{: #vcshcx-deployment-cloud}

클라우드 측 HCX 배치는 {{site.data.keyword.vmwaresolutions_full}} 자동화를 통해 처리합니다. 기본 구성에서는 Fleet 컴포넌트 엔드포인트 연결을 구성하는 데 공용 포트 그룹을 사용합니다. 클라우드 측 Fleet 컴포넌트는 보안이 강화된 어플라이언스이므로 엔드포인트 인터페이스를 공용 IP 주소로 구성하여 배치됩니다. 방화벽 뒤에도 배치할 수 있습니다. 기존 VPN
터널을 사용하여 클라이언트와 클라우드 측이 서로
연결하는 것은 지원되지 않습니다. HCX 엔드포인트 연결에 사설 네트워크를 사용하려면
MPLS와 같은 전용 링크에서 사용할 사설 네트워크 Fleet 배치용으로 HCX 클라우드 측을 주문할 수 있습니다.

## 클라이언트
{: #vcshcx-deployment-client}

클라이언트 측 HCX는 사용자가 배치하며 소스 vCenter에 대한
관리자 레벨 권한이 필요합니다. 이 문서 작성 당시, HCX 클라이언트-서버
관리자 ova는 약 1.7GB입니다. {{site.data.keyword.vmwaresolutions_short}} 콘솔을 사용하여
HCX를 주문하면 클라우드 측에 배치된 HCX 버전과 일치하는
클라이언트 측의 HCX 버전을 다운로드하는 링크가 포함된
URL이 제공됩니다. 이 링크는 클라우드 측 HCX Manager 사용자 인터페이스(UI)에 제공됩니다.

일회성 사용 등록 키도 제공됩니다. 다음 단계를 사용하여 사용 등록을 구성하십시오.

1. 클라우드 측 HCX UI에 제공된 링크에서 HCX 클라이언트(엔터프라이즈)
OVA를 다운로드하십시오.
    1. IBM에서 제공한 HCX 등록 UI를 사용하여 클라우드 측 HCX UI에 로그인합니다.
    2. 클라우드 vCenter ID와 비밀번호를 사용하여 UI에 로그인합니다.
    3. **관리** 탭에서 **요청 다운로드 링크**를 선택하여 클라이언트 측 OVA를 다운로드하십시오. OVA가 배치된 소스 vCenter에 로컬인 “점프 상자”를 사용하여 이 단계를 완료하십시오.
2. vSphere C++ 클라이언트(또는 작동하는 클라이언트 통합 스냅인이 포함된 웹 클라이언트)에 로그인하여 vCenter 가져오기 마법사를 사용하는 OVA를 가져옵니다.
    1. HCX 관리자가 구성된 네트워크에서 소스 vCenter와 인터넷에 모두 액세스할 수 있는지 확인합니다.  
    2. 프롬프트가 표시되면 등록 키를 입력합니다 (클라이언트 도구 스냅인 설정이 있는 경우 웹 클라이언트 사용).  
3. 로그아웃한 다음 vCenter 웹 클라이언트에 다시 로그인합니다. **HCX** 메뉴 선택 아이콘이 홈 화면 메뉴에 표시됩니다.
4. 자체 서명 인증서의 경우 HCX 메뉴 항목을 선택하여 HCX 스냅인 UI에 액세스합니다. **관리** 탭을 선택합니다.
    1. URL에서 인증서를 가져오고 HCX용 {{site.data.keyword.vmwaresolutions_short}} 콘솔에서 제공한 HCX 클라우드 측 등록 URL의 키를 가져오도록 선택합니다.
    2. **대시보드** 탭의 **사이트 페어링** 창에서 **새 사이트 페어링**을 선택하십시오.
    3. 프롬프트를 따라 HCX 클라우드 측 등록 URL 및 클라우드 측 vCenter 관리자 ID와 비밀번호를 제공하십시오.
    4. 계속하여 클라우드 게이트웨이, 계층 2 집선기 및 WAN 최적화 프로그램 등의 Fleet 컴포넌트를 구성하는 사이트 등록 마법사의 프롬프트를 따르십시오.  

클라이언트 측의 경우 **태스크** 메뉴를 사용하여 Fleet 컴포넌트의 배치를 모니터링하십시오. 클라우드 측 배치의 경우 특정 vCenter 서버 인스턴스의 vCenter 웹 UI에 있는 **태스크** 메뉴를 사용하십시오.

어떤 측에서든 배치 실패가
발생하면 Fleet 컴포넌트 배치가 취소되고
삭제됩니다. 실패 원인을 판별하고 나면 클라이언트 측의 HCX vCenter 웹 UI에 있는 **상호 연결** 탭을 클릭한 다음 화면 맨 위에서 **HCX 컴포넌트 설치**를 선택하십시오.

Fleet 컴포넌트를 성공적으로 배치한 후 몇 분이 지나면 CGW 및 L2C 컴포넌트의 터널 상태가 **상호 연결** 탭에서 **작동**으로 표시됩니다.

## 관련 링크
{: #vcshcx-deployment-related}

* [vCenter Server on {{site.data.keyword.cloud_notm}} with Hybridity Bundle 개요](/docs/services/vmwaresolutions/archiref/vcs?topic=vmware-solutions-vcs-hybridity-intro)   
