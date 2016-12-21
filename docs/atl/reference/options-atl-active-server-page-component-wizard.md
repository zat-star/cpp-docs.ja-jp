---
title: "オプション、ATL Active Server Page コンポーネント ウィザード | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.codewiz.class.atl.asp.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL Active Server Page コンポーネント ウィザード、オプション"
ms.assetid: 54f34e26-53c7-4456-9675-cb86e356bde0
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オプション、ATL Active Server Page コンポーネント ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL Active Server Page コンポーネント ウィザードのこのページを使用して、オブジェクトの効率を向上させる機能とエラー サポートについてデザインします。  
  
 ATL プロジェクトおよび ATL COM クラスの詳細については、「[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)」を参照してください。  
  
 **スレッド モデル**  
 スレッドの管理方法を指定します。  既定では、プロジェクトは \[アパートメント\] スレッドを使用します。  
  
 詳細については、「[プロジェクトのスレッド モデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)」を参照してください。  
  
|オプション|説明|  
|-----------|--------|  
|`Single`|オブジェクトでシングルスレッド モデルを使用するように指定します。  シングルスレッド モデルでは、オブジェクトは常にプライマリ COM スレッドで実行されます。  詳細については、「[Single\-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112)」および「[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)」を参照してください。|  
|**\[アパートメント\]**|オブジェクトでアパートメント スレッドを使用するように指定します。  これはシングル スレッド アパートメントと同じ意味です。  アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間にスレッドに対するアパートメントが 1 つ割り当てられますが、複数のオブジェクトに対しては複数のスレッドを使用できます。  各アパートメントは特定のスレッドに結び付けられ、Windows メッセージ ポンプが行われます \(既定\)。<br /><br /> 詳細については、「[Single\-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112)」を参照してください。|  
|**Both**|オブジェクトが作成されたスレッドの種類に応じて、アパートメント スレッドとフリー スレッドのいずれかをオブジェクトで使用できるように指定します。|  
|**Free**|オブジェクトでフリー スレッドを使用するように指定します。  フリー スレッドはマルチスレッド アパートメント モデルと同じ意味です。  詳細については、「[Multithreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421)」を参照してください。|  
|**Neutral** \(Windows 2000 only\)|オブジェクトがマルチスレッド アパートメントのガイドラインに従うようにし、どの種類のスレッドにおいても実行できるように指定します。|  
  
 **\[集約\]**  
 オブジェクトで[集約](http://msdn.microsoft.com/library/windows/desktop/ms686558)を使用するかどうかを指定します。  集約オブジェクトはクライアントに公開するインターフェイスを選択します。そのインターフェイスは、集約オブジェクトによって実装されているものとして公開されます。  集約オブジェクトのクライアントがやり取りするのは集約オブジェクトだけです。  
  
|オプション|説明|  
|-----------|--------|  
|**はい**|オブジェクトが集約できるように指定します。  既定値です。|  
|**いいえ**|オブジェクトが集約されないように指定します。|  
|**\[アグリゲーションのみ\]**|オブジェクトを必ず集約するように指定します。|  
  
 **\[サポート\]**  
 \(追加される要素の記述\)  
  
|オプション|説明|  
|-----------|--------|  
|**ISupportErrorInfo**|[ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) インターフェイスのサポートを作成して、オブジェクトからクライアントにエラー情報を返せるようにします。|  
|**Connection points**|オブジェクトのクラスを [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) から派生させることによって、オブジェクトのコネクション ポイントを有効にします。|  
|**Free\-threaded marshaler**|同一プロセス内のスレッド間のインターフェイス ポインターを効率的にマーシャリングするためのフリー スレッド マーシャラー オブジェクトが作成されます。  スレッド モデルとして \[両方\] または \[フリー\] が指定されているオブジェクトで使用できます。|  
  
## 参照  
 [ATL Active Server Pages コンポーネント ウィザード](../../atl/reference/atl-active-server-page-component-wizard.md)   
 [ATL Active Server Page Component](../../atl/reference/adding-an-atl-active-server-page-component.md)