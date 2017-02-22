---
title: "COleObjectFactory クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleObjectFactory"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス ファクトリ, COleObjectFactory クラス"
  - "COleObjectFactory クラス"
  - "オブジェクト作成, OLE オブジェクト"
  - "オブジェクト [C++], 作成 (OLE を)"
  - "OLE クラス ファクトリ"
  - "OLE オブジェクト"
  - "OLE オブジェクト, 作成"
  - "OLE, クラス ファクトリ"
ms.assetid: ab179c1e-4af2-44aa-a576-37c48149b427
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# COleObjectFactory クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE クラスのファクトリを実装しています。このクラスによって、サーバー、オートメーション オブジェクト、ドキュメントなどの OLE オブジェクトを作成できます。  
  
## 構文  
  
```  
class COleObjectFactory : public CCmdTarget  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[COleObjectFactory::COleObjectFactory](../Topic/COleObjectFactory::COleObjectFactory.md)|`COleObjectFactory` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleObjectFactory::GetClassID](../Topic/COleObjectFactory::GetClassID.md)|このファクトリで作成されるオブジェクトの OLE クラスの ID を返します。|  
|[COleObjectFactory::IsLicenseValid](../Topic/COleObjectFactory::IsLicenseValid.md)|コントロールのライセンスが有効かどうかを判定します。|  
|[COleObjectFactory::IsRegistered](../Topic/COleObjectFactory::IsRegistered.md)|オブジェクト ファクトリが OLE システム DLL に登録するかどうかを示します。|  
|[COleObjectFactory::Register](../Topic/COleObjectFactory::Register.md)|OLE システム DLL でこのオブジェクト ファクトリを登録します。|  
|[COleObjectFactory::RegisterAll](../Topic/COleObjectFactory::RegisterAll.md)|OLE システム DLL のアプリケーション オブジェクトのすべてのファクトリを登録します。|  
|[COleObjectFactory::Revoke](../Topic/COleObjectFactory::Revoke.md)|OLE システム DLL でこのオブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::RevokeAll](../Topic/COleObjectFactory::RevokeAll.md)|OLE システム DLL のアプリケーション オブジェクト ファクトリの登録を取り消します。|  
|[COleObjectFactory::UnregisterAll](../Topic/COleObjectFactory::UnregisterAll.md)|アプリケーションのすべてのオブジェクト ファクトリを登録解除します。|  
|[COleObjectFactory::UpdateRegistry](../Topic/COleObjectFactory::UpdateRegistry.md)|OLE システム レジストリでこのオブジェクト ファクトリを登録します。|  
|[COleObjectFactory::UpdateRegistryAll](../Topic/COleObjectFactory::UpdateRegistryAll.md)|OLE システム レジストリでアプリケーションのすべてのオブジェクト ファクトリを登録します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[COleObjectFactory::GetLicenseKey](../Topic/COleObjectFactory::GetLicenseKey.md)|コントロール DLL からの一意キーが必要です。|  
|[COleObjectFactory::OnCreateObject](../Topic/COleObjectFactory::OnCreateObject.md)|このファクトリの型の新しいオブジェクトを作成するために、フレームワークによって呼び出されます。|  
|[COleObjectFactory::VerifyLicenseKey](../Topic/COleObjectFactory::VerifyLicenseKey.md)|コントロールに埋め込まれたキーがコンテナーに埋め込まれたキーに一致することを確認します。|  
|[COleObjectFactory::VerifyUserLicense](../Topic/COleObjectFactory::VerifyUserLicense.md)|コントロールは、デザイン時のライセンス使用していることを確認します。|  
  
## 解説  
 `COleObjectFactory` のクラスに、次の機能を実行するためのメンバー関数があります:  
  
-   オブジェクトの登録を管理します。  
  
-   OLE システムの登録や、オブジェクトは実行し、メッセージを受信する準備が整っている OLE ランタイムに通知の登録を更新します。  
  
-   ライセンス処理をライセンス開発者と実行時のライセンスされたアプリケーションのデザイン時にコントロールの使用を制限して実装します。  
  
-   OLE システム レジストリでコントロール オブジェクト ファクトリの登録。  
  
 オブジェクトの作成の詳細については、" " [データ オブジェクトとデータ ソース \(OLE\)](../../mfc/data-objects-and-data-sources-ole.md) と [データのオブジェクトとデータ ソース: 作成と破棄](../../mfc/data-objects-and-data-sources-creation-and-destruction.md)を参照してください。  登録に関する詳細については、" " [登録](../../mfc/registration.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 `COleObjectFactory`  
  
## 必要条件  
 **ヘッダー :** afxdisp.h  
  
## 参照  
 [CCmdTarget クラス](../Topic/CCmdTarget%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleTemplateServer クラス](../../mfc/reference/coletemplateserver-class.md)