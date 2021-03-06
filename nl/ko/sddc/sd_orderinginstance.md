---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-15"

---

{:tip: .tip}
{:note: .note}
{:important: .important}

# Cloud Foundation 인스턴스 주문
{: #sd_orderinginstance}

표준 컴퓨팅, 스토리지 및 네트워크구성으로 통합된 소프트웨어 정의 데이터 센터(SDDC) 플랫폼을 배치하려면 VMware Cloud Foundation 인스턴스를 주문하십시오. 초기 주문 중에는 재해 복구를 위한 [Zerto on {{site.data.keyword.cloud}}](/docs/services/vmwaresolutions/services?topic=vmware-solutions-addingzertodr)와 같은 서비스를 추가할 수도 있습니다.

## 요구사항
{: #sd_orderinginstance-req}

다음 태스크를 완료했는지 확인하십시오.
*  **설정** 페이지에 {{site.data.keyword.cloud_notm}} 인프라 인증 정보를 구성했습니다. 자세한 정보는 [사용자 계정 및 설정 관리](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-useraccount)를 참조하십시오.
*  [Cloud Foundation 인스턴스에 대한 요구사항 및 계획](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning)의 요구사항 및 고려사항을 검토했습니다.

인스턴스 주문 또는 배치 중에 설정되는 값은 수정하지 마십시오. 수정하는 경우 인스턴스를 사용할 수 없게 됩니다. 예를 들어, 공용 네트워킹이 종료되는 경우, 서버 및 가상 서버 인스턴스(VSI)가 Vyatta 뒤로 이동하는 경우, IBM CloudBuilder VSI가 중지하거나 삭제된 경우입니다. 또한 인스턴스가 배치된 후 인스턴스 이름, 루트 도메인 이름, 하위 도메인 레이블 또는 호스트 이름 접두부를 변경하지 마십시오.
{:important}

## 시스템 설정
{: #sd_orderinginstance-sys-settings}

Cloud Foundation 인스턴스를 주문할 때는 다음 시스템 설정을 지정해야 합니다.

### 인스턴스 이름
{: #sd_orderinginstance-inst-name}

인스턴스 이름은 다음 요구사항을 충족해야 합니다.
* 영숫자 문자 및 대시(-) 문자만 사용할 수 있습니다.
* 인스턴스 이름은 영문자로 시작하고 영숫자로 끝나야 합니다.
* 인스턴스 이름의 최대 길이는 10자입니다.
* 인스턴스 이름은 계정 내에서 고유해야 합니다.

### 기본 또는 보조
{: #sd_orderinginstance-primary-secondary}

새 기본 인스턴스를 주문할지 또는 기존 기본 인스턴스의 보조 인스턴스를 주문할지 선택하십시오.

## 라이센스 부여 설정
{: #sd_orderinginstance-licensing-settings}

인스턴스의 다음 VMware 컴포넌트에 대한 라이센싱 옵션을 지정하십시오.  
* vCenter Server 라이센스 - Standard
* vSphere 라이센스 - Enterprise Plus
* NSX 라이센스 - Enterprise
* vSAN 라이센스: Advanced 또는 Enterprise 에디션 선택

비즈니스 파트너 사용자의 경우, vCenter Server 라이센스(Standard 에디션), vSphere 라이센스(Enterprise Plus 에디션), NSX 라이센스 및 vSAN 라이센스가 사용자를 대신하여 포함 및 구매됩니다. 그러나 vSAN 라이센스의 에디션은 지정해야 합니다.

비즈니스 파트너가 아닌 사용자의 경우에는 **구매에 포함**을 선택하여 이 컴포넌트에 대해 IBM 제공 VMware 라이센스를 사용하거나, **라이센스를 제공함**을 선택하고 고유한 라이센스 키를 입력하여 고유한 라이센스를 가져올(BYOL) 수 있습니다.

## Bare Metal Server 설정
{: #sd_orderinginstance-bare-metal}

### 데이터 센터 위치
{: #sd_orderinginstance-dc-location}

인스턴스가 호스팅되는 {{site.data.keyword.CloudDataCent_notm}}를 선택하십시오.

### Skylake
{: #sd_orderinginstance-skylake}

**Skylake**를 선택하는 경우 필요에 따라 Bare Metal Server의 CPU 및 RAM 조합을 선택할 수 있습니다.

표 1. Skylake {{site.data.keyword.baremetal_short}}의 옵션

| CPU 모델 옵션  |RAM 옵션       |
|:------------- |:------------- |
|듀얼 Intel Xeon Silver 4110 프로세서 / 총 16개의 코어, 2.1GHz | 128GB, 192GB, 384GB, 768GB, 1.5TB |
|듀얼 Intel Xeon Gold 5120 프로세서 / 총 28개의 코어, 2.2GHz | 128GB, 192GB, 384GB, 768GB, 1.5TB |
|듀얼 Intel Xeon Gold 6140 프로세서 / 총 36개의 코어, 2.3GHz | 128GB, 192GB, 384GB, 768GB, 1.5TB |

### Broadwell
{: #sd_orderinginstance-broadwell}

**Broadwell**을 선택하는 경우 필요에 따라 Bare Metal Server의 CPU 및 RAM 조합을 선택할 수 있습니다.

표 2. Broadwell {{site.data.keyword.baremetal_short}}의 옵션

| CPU 모델 옵션        |RAM 옵션       |
|:------------- |:------------- |
| 듀얼 Intel Xeon E5-2620 v4 / 총 16개의 코어, 2.1GHz |128GB, 256GB, 512GB, 768GB, 1.5TB |
| 듀얼 Intel Xeon E5-2650 v4 / 총 24개의 코어, 2.2GHz |128GB, 256GB, 512GB, 768GB, 1.5TB |
| 듀얼 Intel Xeon E5-2690 v4 / 총 28개의 코어, 2.6GHz |128GB, 256GB, 512GB, 768GB, 1.5TB |
| 쿼드 Intel Xeon E7-4820 v4 / 총 40개의 코어, 2.0GHz |128GB, 256GB, 512GB, 1TB, 2TB, 3TB |
| 쿼드 Intel Xeon E7-4850 v4 / 총 64개의 코어, 2.1GHz |128GB, 256GB, 512GB, 1TB, 2TB, 3TB |

### Bare Metal Server 수
{: #sd_orderinginstance-bare-metal-number}

Cloud Foundation 인스턴스는 초기 배치 시 네 개의 Bare Metal Server로 구성됩니다. 사용자는 주문 시에 Bare Metal Server 수를 변경할 수 없습니다.

## 스토리지 설정
{: #sd_orderinginstance-storage}

Cloud Foundation 인스턴스의 경우, VMware vSAN 스토리지만 주문할 수 있습니다.

**Skylake** 또는 **Broadwell** Bare Metal Server 구성을 선택하는 경우 인스턴스에 대한 vSAN 스토리지를 사용자 정의할 수 있습니다. 다음 vSAN 설정을 지정하십시오.
* **vSAN 용량 디스크의 디스크 유형 및 크기**: 필요한 용량 디스크에 대한 옵션을 선택하십시오.
* **vSAN 용량 디스크 수**: 추가할 용량 디스크 수를 지정하십시오.
* 용량 디스크를 8개 한계 이상으로 추가하려는 경우 **고성능 Intel Optane** 상자를 선택하십시오. 이 옵션은 총 10개 용량 디스크에 대해 2개의 추가 용량 디스크 베이를 제공하며 짧은 대기 시간과 높은 IOPS 처리량이 필요한 워크로드에 유용합니다.

  **고성능 Intel Optane** 옵션은 Skylake CPU 모델 듀얼 Intel Xeon Gold 5120 및 듀얼 Intel Xeon Gold 6140에 대해서만 사용 가능합니다.
  {:note}

* **vSAN 캐시 디스크의 디스크 유형** 및 **vSAN 캐시 디스크 수** 값을 검토하십시오. 이러한 값은 **고성능 Intel Optane** 상자를 선택했는지 여부에 따라 달라집니다.

## 네트워크 인터페이스 설정
{: #sd_orderinginstance-network-interface}

Cloud Foundation 인스턴스를 주문할 때는 다음 네트워크 인터페이스 설정을 지정해야 합니다.

### 호스트 이름 접두부
{: #sd_orderinginstance-hostname-prefix}

호스트 이름 접두부는 다음 요구사항을 충족해야 합니다.
*  영숫자 문자 및 대시(-) 문자만 사용할 수 있습니다.
*  호스트 이름 접두부는 영숫자 문자로 시작하고 끝나야 합니다.
*  호스트 이름 접두부의 최대 길이는 10자입니다.

### 하위 도메인 레이블
{: #sd_orderinginstance-subdomain-label}

하위 도메인 레이블은 다음 요구사항을 충족해야 합니다.
*  영숫자 문자 및 대시(-) 문자만 사용할 수 있습니다.
*  하위 도메인 레이블은 영문자로 시작하고 영숫자로 끝나야 합니다.
*  하위 도메인 레이블의 최대 길이는 10자입니다.
*  하위 도메인 레이블은 계정 내에서 고유해야 합니다.

### 도메인 이름
{: #sd_orderinginstance-domain-name}

루트 도메인 이름은 다음 요구사항을 충족해야 합니다.
* 도메인 이름은 마침표(.)로 구분된 두 개 이상의 문자열로 구성되어야 합니다.
* 첫 번째 문자열은 영문자로 시작하고 영숫자로 끝나야 합니다.
* 마지막 문자열을 제외한 모든 문자열은 영숫자 및 대시(-) 문자만 포함할 수 있습니다.
* 마지막 문자열은 영문자만 포함할 수 있습니다.
* 마지막 문자열의 길이는 2 - 24자 사이여야 합니다.

호스트 및 가상 머신(VM)에 대한 FQDN(Fully Qualified Domain Name)의 최대 길이는 50자입니다. 도메인 이름은 이 최대 길이를 포함할 수 있어야 합니다.
{:note}

### 네트워크 설정의 값 형식
{: #sd_orderinginstance-network-settings-value-format}

다음 표에 표시되어 있는 바와 같이, 도메인 이름 및 하위 도메인 레이블은 인스턴스의 사용자 이름 및 서버 이름을 생성하는 데 사용됩니다.

표 3. 사용자 이름, 도메인 이름 및 서버 이름의 값 형식

|이름        |값 형식      |
  |:------------- |:------------- |
  |도메인 이름 | `<root_domain>` |  
  |완전한 ESXi 서버 이름 | `<host_prefix><n>.<subdomain_label>.<root_domain>`, 여기서 `<n>`은 ESXi 서버의 순서입니다. 최대 길이는 50자입니다. |   
  |vCenter Server 로그인 사용자 이름 | `<user_id>@<root_domain>`(Microsoft Active Directory 사용자) 또는 `administrator@vsphere.local` |
  |vCenter Server FQDN |`vcenter-1.<subdomain_label>.<root_domain>`. 최대 길이는 50자입니다. |  
  |SDDC Manager FQDN |`sddcmanager.<subdomain_label>.<root_domain>`. 최대 길이는 50자입니다. |
  |SSO(Single Sign-On) 사이트 이름 | `<subdomain_label>`
  |PSC FQDN |`PSC-<subdomain_label>.<subdomain_label>.<root_domain>`. 최대 길이는 50자입니다. |  

  SDDC Manager FQDN은 공개적으로 분석될 수 없습니다. 그렇지 않으면, Cloud Foundation 인스턴스 구성은 실패할 수 있고 복구할 수 없습니다. 도메인 이름을 지정하기 전에 [루트 도메인 이름 선택 시 고려사항](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-trbl_limitations#considerations-when-choosing-a-root-domain-name-for-cloud-foundation-instances)을 검토하십시오.

### VLAN
{: #sd_orderinginstance-vlans}

네트워크 설정은 **새 VLAN 주문** 또는 **기존 VLAN 선택**의 선택에 따라 달라집니다.

인스턴스 주문에 한 개의 공용 VLAN 및 두 개의 사설 VLAN이 필요합니다. 두 개의 사설 VLAN이 각 Bare Metal Server에 선택됩니다.

#### 새 VLAN 주문
{: #sd_orderinginstance-new-vlans}

하나의 새 공용 VLAN 및 두 개의 새 사설 VLAN 주문을 선택하십시오.

#### 기존 VLAN 선택
{: #sd_orderinginstance-existing-vlans}

선택한 {{site.data.keyword.CloudDataCent_notm}}에 따라 기존 공용 및 사설 VLAN을 사용할 수 있습니다.

기존 공용 및 사설 VLAN을 재사용하도록 선택하는 경우에는 VLAN 및 서브넷을 지정하십시오.
  * **공용 VLAN**은 공용 네트워크 액세스를 위한 것입니다.
  * **사설 VLAN**은 {{site.data.keyword.cloud_notm}} 내의 데이터 센터 및 서비스 간의 연결을 위한 것입니다.
  * **보조 사설 VLAN**은 vSAN과 같은 VMware 기능을 위한 것입니다.
  * **기본 서브넷**은 공용 네트워크 액세스를 위한 실제 호스트에 지정됩니다.
  * **사설 기본 서브넷**은 관리 트래픽을 위한 실제 호스트에 지정됩니다.

선택된 VLAN의 방화벽 구성이 관리 데이터 트래픽을 차단하지 않는지 확인하십시오. ESXi 서버는 혼합 팟(Pod) VLAN에서 프로비저닝될 수 없으므로 선택한 모든 VLAN이 동일한 팟(Pod)에 있는지 확인하십시오.
{:important}

## Services
{: #sd_orderinginstance-addon-services}

Cloud Foundation 인스턴스를 주문하는 경우 추가 기능 서비스도 주문할 수 있습니다. 사용 가능한 서비스에 대한 자세한 정보는 [Cloud Foundation 인스턴스에 대한 서비스](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_planning#services-for-cloud-foundation-instances)를 참조하십시오.

## 주문 요약
{: #sd_orderinginstance-order-summary}

인스턴스 및 추가 기능 서비스에 대해 사용자가 선택한 구성에 따라, 예상 비용이 즉시 생성되어 오른쪽 분할창에 표시됩니다. 오른쪽 분할창에서 **가격 세부사항**을 클릭하여 예상 세부사항을 제공하는 PDF 문서를 생성하십시오.

## Cloud Foundation 인스턴스를 주문하는 프로시저
{: #sd_orderinginstance-procedure}

1. {{site.data.keyword.cloud_notm}} 카탈로그의 왼쪽 탐색 분할창에 있는 **VMware**를 클릭한 후 **가상 데이터 센터** 섹션에 있는 **Cloud Foundation**을 클릭하십시오.
2. **VMware Cloud Foundation on IBM Cloud** 페이지에서 **작성**을 클릭하십시오.
3. **Cloud Foundation** 페이지에서 인스턴스 이름을 입력하십시오.
4. 인스턴스 유형을 선택하십시오.
   * 환경에 하나의 인스턴스를 배치하거나 다중 사이트 토폴로지에 첫 번째 인스턴스를 배치하려면 **기본 인스턴스**를 클릭하십시오.
   * 고가용성을 위해 인스턴스를 환경의 기존(기본) 인스턴스에 연결하려면 **보조 인스턴스**를 클릭하십시오. 다음 단계를 완료하십시오.
     1. 보조 인스턴스를 연결할 기본 인스턴스를 선택하십시오.
     2. 기본 인스턴스 V2.5 이상의 경우 **기본 인스턴스 PSC의 관리자 비밀번호**에 대한 값을 입력하십시오.
     3. 기본 인스턴스 V2.4 이하인 경우 미리 채워진 **기본 인스턴스 PSC의 관리자 비밀번호** 필드의 값이 올바른지 확인하십시오.
5. 인스턴스 컴포넌트에 대한 라이센스 설정을 완료하십시오.
   *  IBM 제공 라이센스를 사용하려면 **구매에 포함**을 선택하십시오.
   *  자신의 라이센스를 사용하려면 **라이센스를 제공함**을 선택하고 라이센스 키를 입력하십시오.  
6. Bare Metal Server 설정을 완료하십시오.
   1. {{site.data.keyword.CloudDataCent_notm}}를 선택하여 인스턴스를 호스팅하십시오.
   2. Bare Metal Server 구성을 선택한 후 CPU 모델 및 RAM 크기를 지정하십시오.
7. 스토리지 구성을 완료하십시오.
   1. vSAN 용량 및 캐시 디스크에 대한 디스크 유형과 디스크 수를 지정하십시오.
   2. 더 많은 스토리지를 원하는 경우 **Intel Optane을 사용한 고성능** 선택란을 선택하십시오.
8. 네트워크 인터페이스 설정을 완료하십시오.
   1. 호스트 이름 접두부, 하위 도메인 레이블 및 루트 도메인 이름을 입력하십시오. 보조 인스턴스의 경우에는 도메인 이름이 자동으로 입력됩니다.
   2. VLAN 설정을 선택하십시오.
      * 새 공용 및 사설 VALN을 주문하려면 **새 VLAN 주문**을 클릭하십시오.
      * 기존 공용 및 사설 VLAN이 사용 가능한 경우 이들을 재사용하려면 **기존 VLAN 선택**을 클릭하고 VLAN 및 서브넷을 지정하십시오.

9. 추가 기능 서비스 카드를 클릭하여 인스턴스에 배치할 해당 추가 기능 서비스를 선택하십시오. 서비스가 구성을 필요로 하는 경우에는 서비스 고유 설정을 완료하고 팝업 구성 창의 **서비스 추가**를 클릭하십시오. 서비스의 설정을 제공하는 방법에 대한 자세한 정보는 해당 주문 서비스 주제를 참조하십시오.

10. 주문하기 전에 **주문 요약** 페이지에서 인스턴스 구성을 확인하십시오.
    1. 인스턴스의 설정을 검토하십시오.
    2. 인스턴스의 예상 비용을 검토하십시오. PDF 요약을 생성하려면 **가격 세부사항**을 클릭하십시오. 주문 요약을 저장하거나 인쇄하려면 PDF 창의 오른쪽 상단에 있는 **인쇄** 또는 **다운로드** 아이콘을 클릭하십시오.
    3. 비용이 청구되는 계정이 올바른지 확인한 후 **아래 나열된 계정에 비용이 청구될 것임을 이해함** 선택란을 선택하십시오.
    4. 주문에 적용되는 이용 약관에 대한 링크를 클릭하십시오. 이러한 이용 약관에 동의하는지 확인한 후 **아래 나열된 서드파티 서비스 계약을 읽었으며 이에 동의함** 선택란을 선택하십시오.
    5. **프로비저닝**을 클릭하십시오.

## 결과
{: #sd_orderinginstance-results}

인스턴스의 배치가 자동으로 시작됩니다. 주문이 처리 중이라는 확인을 받은 후 인스턴스 세부사항을 보고 배치의 상태를 확인할 수 있습니다.

인스턴스가 성공적으로 배치된 경우에는 [Cloud Foundation 인스턴스의 기술 스펙](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_cloudfoundationoverview#technical-specifications-for-cloud-foundation-instances)에서 설명된 컴포넌트가 VMware 가상 플랫폼에 설치됩니다. 기본적으로 주문한 ESXi 서버는 **SDDC-Cluster**로 그룹화됩니다. 추가 기능 서비스를 주문한 경우 주문이 완료된 후 서비스의 배치가 시작됩니다.

인스턴스를 사용할 준비가 되면 인스턴스의 상태가 **사용할 준비가 됨**으로 변경되고 이메일로 알림을 받습니다.

보조 인스턴스를 주문하는 경우 보조 인스턴스 주문이 완료된 후 기본 인스턴스(보조 인스턴스로 링크됨)의 VMware vSphere Web Client가 다시 시작될 수 있습니다.

## 수행할 작업
{: #sd_orderinginstance-next}

주문한 Cloud Foundation 인스턴스를 보고 관리하십시오.

{{site.data.keyword.slportal}} 또는 콘솔 이외의 다른 수단이 아닌, {{site.data.keyword.vmwaresolutions_short}} 콘솔에서만 {{site.data.keyword.cloud_notm}} 계정에 작성되는 {{site.data.keyword.vmwaresolutions_short}} 컴포넌트를 관리해야 합니다. {{site.data.keyword.vmwaresolutions_short}} 콘솔 외부에서 컴포넌트를 변경하는 경우 변경사항은 콘솔과 동기화되지 않습니다.
{:important}

**주의:** {{site.data.keyword.vmwaresolutions_short}} 콘솔 외부에서 {{site.data.keyword.vmwaresolutions_short}} 컴포넌트(인스턴스 주문 시 {{site.data.keyword.cloud_notm}} 계정에 설치된)를 관리하면 환경이 불안정해질 수 있습니다. 이러한 관리 활동에는 다음이 포함됩니다.

*  컴포넌트 추가, 수정, 리턴 또는 제거
*  ESXi 서버 추가 또는 제거를 통한 인스턴스 용량의 확장 또는 축소
*  컴포넌트 전원 끄기
*  서비스 다시 시작

   이 활동에 대한 예외에는 {{site.data.keyword.slportal}}의 공유 스토리지 파일 공유 관리가 포함됩니다. 이러한 활동에는 공유 스토리지 파일 공유 주문, 삭제(마운트된 경우 데이터 저장소에 영향을 줄 수 있음), 권한 부여 및 마운트가 포함됩니다.

## 관련 링크
{: #sd_orderinginstance-related}

* [{{site.data.keyword.cloud_notm}} 계정 등록](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-signing_softlayer_account)
* [Cloud Foundation 인스턴스 보기](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_viewinginstances)
* [Cloud Foundation 인스턴스의 클러스터 추가, 보기 및 삭제](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-adding-and-viewing-clusters-for-cloud-foundation-instances)
* [Cloud Foundation 인스턴스에 대한 용량 확장 및 축소](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservers)
* [Cloud Foundation 인스턴스에 대한 서비스 주문, 보기 및 제거](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_addingremovingservices)
* [Cloud Foundation 인스턴스 삭제](/docs/services/vmwaresolutions/sddc?topic=vmware-solutions-sd_deletinginstance)
* [BYOL에 대한 FAQ](/docs/services/vmwaresolutions/vmonic?topic=vmware-solutions-faq_byol)
