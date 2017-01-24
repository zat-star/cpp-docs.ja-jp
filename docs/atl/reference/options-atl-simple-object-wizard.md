---
title: "オプション、ATL シンプル オブジェクト ウィザード | Microsoft Docs"
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
  - "vc.codewiz.class.atl.simple.options"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL シンプル オブジェクト ウィザード、オプション"
ms.assetid: 125fe179-942d-4181-8b82-33e92e1fd779
caps.latest.revision: 14
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オプション、ATL シンプル オブジェクト ウィザード
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ATL シンプル オブジェクト ウィザードのこのページを使用して、オブジェクトの効率を向上させる機能とエラー サポートをデザインします。  
  
 ATL プロジェクトおよび ATL COM クラスの詳細については、「[ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)」を参照してください。  
  
 **\[スレッド モデル\]**  
 スレッドの管理方法を指定します。  既定では、プロジェクトは \[アパートメント\] スレッドを使用します。  
  
 詳細については、「[プロジェクトのスレッド モデルの指定](../../atl/specifying-the-threading-model-for-a-project-atl.md)」を参照してください。  
  
|オプション|説明|  
|-----------|--------|  
|`Single`|オブジェクトが常にプライマリ COM スレッドで実行されるように指定します。  詳細については、「[Single\-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112)」および「[InprocServer32](http://msdn.microsoft.com/library/windows/desktop/ms682390)」を参照してください。|  
|**Apartment**|オブジェクトでアパートメント スレッドを使用するように指定します。  これはシングル スレッド アパートメントと同じ意味です。  アパートメント スレッド コンポーネントの各オブジェクトには、オブジェクトの有効期間にスレッドに対するアパートメントが 1 つ割り当てられますが、複数のオブジェクトに対しては複数のスレッドを使用できます。  各アパートメントは特定のスレッドに結び付けられ、Windows メッセージ ポンプが行われます \(既定\)。<br /><br /> 詳細については、「[Single\-Threaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms680112)」を参照してください。|  
|**Both**|オブジェクトが作成されたスレッドの種類に応じて、アパートメント スレッドとフリー スレッドのいずれかをオブジェクトで使用できるように指定します。|  
|**Free**|オブジェクトでフリー スレッドを使用するように指定します。  フリー スレッドはマルチスレッド アパートメント モデルと同じ意味です。  詳細については、「[Multithreaded Apartments](http://msdn.microsoft.com/library/windows/desktop/ms693421)」を参照してください。|  
|**Neutral** \(Windows 2000 only\)|オブジェクトがマルチスレッド アパートメントのガイドラインに従うようにし、どの種類のスレッドにおいても実行できるように指定します。|  
  
 **\[集約\]**  
 オブジェクトで[集約](http://msdn.microsoft.com/library/windows/desktop/ms686558)を使用するかどうかを指定します。  集約オブジェクトはクライアントに公開するインターフェイスを選択します。そのインターフェイスは、集約オブジェクトによって実装されているものとして公開されます。  集約オブジェクトのクライアントがやり取りするのは集約オブジェクトだけです。  
  
|オプション|説明|  
|-----------|--------|  
|あり|オブジェクトが集約できるように指定します。  既定値です。|  
|いいえ|オブジェクトが集約されないように指定します。|  
|Only|オブジェクトを必ず集約するように指定します。|  
  
 **\[インターフェイス\]**  
 オブジェクトがサポートするインターフェイスの種類を指定します。  既定では、オブジェクトはデュアル インターフェイスをサポートします。  
  
|オプション|説明|  
|-----------|--------|  
|**Dual**|オブジェクトがデュアル インターフェイスをサポートするように指定します。オブジェクトの vtable にはカスタム インターフェイス関数と遅延バインディングの `IDispatch` メソッドが含まれます。  COM クライアントと[オートメーション コントローラー](../../mfc/automation-clients.md)の両方からオブジェクトにアクセスできます。  既定値です。|  
|**Custom**|オブジェクトがカスタム インターフェイスをサポートするように指定します。オブジェクトの vtable にはカスタム インターフェイス関数が含まれます。  特にプロセス間にまたがっている場合、カスタム インターフェイスはデュアル インターフェイスよりも高速です。<br /><br /> -   **Automation compatible** は、オートメーション コントローラーがカスタム インターフェイスをサポートするオブジェクトにアクセスできるようにします。|  
  
 **\[サポート\]**  
 オブジェクトのその他のサポートを指定します。  
  
|オプション|説明|  
|-----------|--------|  
|**ISupportErrorInfo**|[ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md) インターフェイスのサポートを作成して、オブジェクトからクライアントにエラー情報を返せるようにします。|  
|**Connection points**|オブジェクトのクラスを [IConnectionPointContainerImpl](../Topic/IConnectionPointContainerImpl%20Class.md) から派生させることによって、オブジェクトのコネクション ポイントを有効にします。|  
|**Free\-threaded marshaler**|同一プロセス内のスレッド間のインターフェイス ポインターを効率的にマーシャリングするためのフリー スレッド マーシャラー オブジェクトが作成されます。  スレッド モデルとして \[両方\] が指定されているオブジェクトで使用できます。|  
|**IObjectWithSite \(IE オブジェクト サポート\)**|オブジェクトとコンテナー内のサイト間の通信をサポートする簡単な方法を提供する [IObjectWithSiteImpl](../../atl/reference/iobjectwithsiteimpl-class.md) を実装します。|  
  
## 参照  
 [ATL シンプル オブジェクト ウィザード](../../atl/reference/atl-simple-object-wizard.md)   
 [ATL Simple Object](../../atl/reference/adding-an-atl-simple-object.md)   
 [In\-Process Server Threading Issues](http://msdn.microsoft.com/library/windows/desktop/ms687205)