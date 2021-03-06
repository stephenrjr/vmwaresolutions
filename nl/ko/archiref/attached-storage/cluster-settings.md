---

copyright:

  years:  2016, 2019

lastupdated: "2019-02-28"

subcollection: vmware-solutions


---

# 클러스터 설정
{: #cluster-settings}

연결된 스토리지 추가 전에는 vCenter Server 솔루션이 vSphere DRS(Distributed Resource Scheduler) 및 vSphere HA(High Availability)와 같은 고급 기능을 사용하지 못했습니다. NFS 연결 스토리지 디바이스를 추가하면 이러한 기능이 다음 섹션에 나열된 설정으로 클러스터에서 사용 가능합니다.

## vSphere Distributed Resource Scheduler
{: #cluster-settings-vsphere-drs}

클러스터에서 vSphere DRS를 켜면, 로드 밸런싱과 전원 관리라는 두 가지 기본 기능을 사용할 수 있습니다.

### 로드 밸런싱
{: #cluster-settings-load-balance}

로드 밸런싱을 사용하면 클러스터의 모든 호스트 및 가상 머신(VM)에 대한 CPU와 메모리 리소스 분배 및 사용이 지속적으로 모니터됩니다. DRS는 클러스터의 리소스 풀과 VM의 속성 및 현재 수요를 고려하여 이러한 메트릭을 이상적 리소스 사용량과 비교합니다. 그런 다음 완료하거나, 필요한 경우 VM 마이그레이션을 수행하는 것이 좋습니다.

먼저 클러스터에서 VM에 전원이 공급되면 DRS가 해당 호스트에 VM을 배치하거나 권장사항을 작성하여 적절한 로드 밸런싱을 유지보수하려고 시도합니다. 배치 또는 권장사항 설정은 클러스터 설정의 DRS 자동화 섹션에 설정됩니다.

이 디자인에서 DRS 자동화 레벨은 완전히 자동화됨으로 설정되므로 VM에 전원이 공급되면 이 VM이 용량이 충분한 호스트에 자동으로 배치됩니다. VM은 하나의 호스트에서 다른 호스트로 자동으로 마이그레이션되어 클러스터를 로드 밸런싱합니다. 또한 DRS 클러스터의 마이그레이션 임계값은 우선순위 1, 우선순위 2 및 우선순위 3 권장사항이 적용되도록 보수적과 적극적의 중간으로 설정됩니다. vCenter Server는 적어도 클러스터의 로드 밸런스를 개선합니다.

다음 표에는 VMware vSphere Web Client의 vSphere DRS 클러스터에 대한 설정이 표시됩니다.

표 1. vSphere DRS 클러스터의 DRS 자동화 설정

|설정             |값  |
|:------------------- |:------ |
| vSphere DRS 켜기 | 선택됨 |
| 자동화 레벨 | 완전한 자동화 |
| 마이그레이션 임계값 | 우선순위 1, 우선순위 2 및 우선순위 3 권장사항 적용 |
| 개별 시스템 자동화 레벨 사용 | 선택됨, 15ms로 설정됨 |

vSphere Web Client에서 이러한 설정을 구성하는 데 대한 자세한 정보는 [vSphere Web Client에서 가상 머신의 사용자 정의 자동화 레벨 설정](https://docs.vmware.com/en/VMware-vSphere/5.5/com.vmware.vsphere.resmgmt.doc/GUID-C21C0609-923B-46FB-920C-887F00DBCAB9.html)을 참조하십시오.

클러스터의 자동화 레벨 및 마이그레이션 임계값과 함께 이 디자인에서는 VM 자동화를 사용하므로 개별 VM당 값을 대체할 수 있습니다. VM을 보다 세부적으로 제어하여 VM의 로드 밸런싱을 더 우선할 수 있습니다.

### 전원 관리
{: #cluster-settings-power-mgmt}

VMware Distributed Power Management 기능을 사용하면, DRS가 클러스터 레벨 및 호스트 레벨 용량을 클러스터 VM의 수요(최근 히스토리 수요 포함)와 비교합니다. 전원 관리 기능은 충분한 초과 용량이 있는 경우 호스트를 대기 전원 모드에 두거나(또는 권장) 용량이 필요한 경우 호스트에 전원을 공급합니다(또는 권장). 결과로 발생한 호스트 전원 상태 권장사항에 따라 VM을 호스트로/로부터 마이그레이션해야 합니다.
이 디자인에서는 클러스터의 호스트에 전원을 공급하거나 차단하는 경우의 운영상 또는 재정적 이점이 없으므로 전원 관리는 사용되지 않습니다.

## vSphere High Availability
{: #cluster-settings-vsphere-ha}

vSphere는 VM 및 이 VM이 상주하는 호스트를 클러스터로 풀링하여 VM에 대한 고가용성을 제공합니다. 클러스터의 호스트는 모니터되며 장애가 발생하는 경우 장애가 발생한 호스트의 VM이 대체 호스트에서 다시 시작됩니다.
이 디자인에서는 클러스터에서 호스트 모니터링 및 VM 모니터링과 함께 vSphere High Availability이 사용됩니다.

### 호스트 모니터링
{: #cluster-settings-host-monitor}

호스트 모니터링을 통해 클러스터의 호스트가 네트워크 하트비트를 교환할 수 있으며 장애 발견 시 vSphere HA를 사용할 수 있습니다. 이 기능은 이 디자인에서 사용 가능합니다.

### 가상 머신 모니터링
{: #cluster-settings-machine-monitor}

VM 모니터링 기능은 VMware 도구가 게스트 운영 체제 가용성을 위해 프록시로 캡처하는 하트비트 정보를 사용합니다. VM 모니터링을 통해 vSphere HA는 더 이상 하트비트 기능이 없는 개별 VM을 자동으로 재설정하거나 다시 시작할 수 있습니다. 이 디자인은 VM 및 애플리케이션 모니터링을 둘 다 사용합니다.

#### 장애 조건 및 VM 응답
{: #cluster-settings-failure-conditions}

장애 조건은 VM에 장애가 발생한 방식과 각 장애에 대한 응답을 정의합니다. 이 디자인에서 VM 다시 시작 우선순위는 중간으로 설정됩니다. 다시 시작 우선순위가 워크로드의 중요도와 일치하도록 이 값을 검토하고 설정을 조정하십시오. 또한 VM이 클러스터의 격리된 호스트에 의해 영향을 받지 않도록 호스트 격리에 대한 응답이 “VM 전원 차단 및 다시 시작”으로 설정됩니다. 이 설정에 대한 나머지 값은 기본값으로 설정됩니다.

다음 표에는 VMware vSphere Web Client의 vSphere HA 클러스터에 대한 설정이 표시됩니다.

표 2. vSphere HA 클러스터에 대한 장애 조건 및 VM 응답 설정

|설정             |값  |
|:------------------- |:------ |
| VM 다시 시작 우선순위 |중간 |
| 호스트 격리에 대한 응답 | VM 전원 차단 및 다시 시작 |
| PDL(Permanent Device Loss)을 사용하는 데이터 저장소에 대한 응답 | 사용 안함 |
| APD(All Paths Down)를 사용하는 데이터 저장소에 대한 응답 | 사용 안함 |
| APD 제한시간 후 APD 복구에 대한 응답 | 사용 안함 |
| VM 모니터링 감도 | 사용자 정의 |
| 장애 간격 | 50초 |
| 최소 작동 시간 | 90초 |
| 최대 VM당 재설정 수 |10 |
| 최대 재설정 시간 범위 | 1시간 내 |

vSphere Web Client에서 이러한 설정을 구성하는 데 대한 자세한 정보는 [가상 머신 응답 구성](https://docs.vmware.com/en/VMware-vSphere/6.0/com.vmware.vsphere.avail.doc/GUID-3DAED2B1-55B8-4877-BD0F-BC57C10A516C.html)을 참조하십시오.

#### 허가 제어
{: #cluster-settings-admin-control}

vCenter Server는 허가 제어를 통해 충분한 리소스가 클러스터에서 사용 가능한지 확인하여 장애 복구 보호를 제공하고 VM 리소스 예약이 준수되는지 확인합니다. 이 디자인에서 장애 복구 용량은 클러스터 리소스의 백분율을 지정하여 예약됩니다. 정의된 장애 복구 용량은 25% CPU 및 25% 메모리로 설정됩니다.

#### 데이터 저장소 하트비트
{: #cluster-settings-datastore}

vSphere HA는 데이터 저장소 하트비트를 사용하여 장애가 발생한 호스트와 네트워크 파티션에 상주하는 호스트를 구분합니다. 데이터 저장소 하트비트를 사용하면 vSphere HA가 관리 네트워크 파티션 발생 시 호스트를 모니터하고 발생한 장애에 대해 계속 응답할 수 있습니다. 이 디자인에서 하트비트 데이터 저장소 선택 정책은 “호스트에서 액세스 가능한 데이터 저장소 자동 선택”으로 설정됩니다.

## 관련 링크
{: #cluster-settings-related}

* [솔루션 개요](/docs/services/vmwaresolutions/archiref/solution?topic=vmware-solutions-solution_overview)
