---
title: "ランタイム オブジェクト モデル サービス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ランタイム オブジェクト モデル サービス マクロ"
ms.assetid: 4a3e79df-2ee3-43a4-8193-20298828de85
caps.latest.revision: 15
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ランタイム オブジェクト モデル サービス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CObject](../Topic/CObject%20Class.md) クラスと [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md) クラスは、ランタイム クラス情報へのアクセス、シリアル化、オブジェクトの動的作成などの複数のオブジェクト サービスをカプセル化します。  `CObject` クラスから派生したすべてのクラスは、この機能を継承します。  
  
 ランタイム クラス情報にアクセスすることにより、実行時にオブジェクトのクラスについての情報を確認できます。  関数の引数の特別な型チェックが必要なときや、オブジェクトのクラスに基づく特別な目的のコードを作る必要があるときは、実行時にオブジェクトのクラスを確認できると便利です。  ランタイム クラス情報は、C\+\+ 言語では直接サポートされていません。  
  
 シリアル化とは、オブジェクトの内容をファイルに書き込んだり、ファイルから読み取ったりする処理のことです。  シリアル化を使うと、アプリケーションが終了した後でもオブジェクトの内容を保存できます。  その後、アプリケーションが再実行されたときに、オブジェクトをファイルから読み込むことができます。  このようなデータ オブジェクトを "永続化された" オブジェクトと呼びます。  
  
 オブジェクトの動的作成では、指定するクラスのオブジェクトを実行時に作成できます。  たとえば、ドキュメント、ビュー、およびフレーム オブジェクトはフレームワークにより動的に作られる必要があるため、動的生成がサポートされる必要があります。  
  
 ランタイム クラス情報、シリアル化、および動的生成をサポートする MFC ライブラリのマクロの一覧を次の表に示します。  
  
 これらのランタイム オブジェクト サービスとシリアル化の詳細については、「[ランタイム クラス情報へのアクセス方法](../../mfc/accessing-run-time-class-information.md)」を参照してください。  
  
### ランタイム オブジェクト モデル サービス マクロ  
  
|||  
|-|-|  
|[DECLARE\_DYNAMIC](../Topic/DECLARE_DYNAMIC.md)|ランタイム クラス情報へのアクセスを可能にします。クラスの宣言の中で使用する必要があります。|  
|[DECLARE\_DYNCREATE](../Topic/DECLARE_DYNCREATE.md)|動的生成、およびランタイム クラス情報へのアクセスを可能にします。クラスの宣言の中で使用する必要があります。|  
|[DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md)|シリアル化、およびランタイム クラス情報へのアクセスを可能にします。クラスの宣言の中で使う必要があります。|  
|[IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md)|ランタイム クラス情報へのアクセスを可能にします。クラスの実装の中で使用する必要があります。|  
|[IMPLEMENT\_DYNCREATE](../Topic/IMPLEMENT_DYNCREATE.md)|動的生成、およびランタイム クラス情報へのアクセスを可能にします。クラスの実装の中で使用する必要があります。|  
|[IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)|シリアル化、およびランタイム クラス情報へのアクセスを可能にします。クラスの実装の中で使用する必要があります。|  
|[RUNTIME\_CLASS](../Topic/RUNTIME_CLASS.md)|指定されたクラスに対応する `CRuntimeClass` 構造体を返します。|  
  
 OLE では、多くの場合、実行時のオブジェクトの動的生成を必要とします。  たとえば、OLE サーバー アプリケーションは、クライアントからの要求に対して動的に OLE 項目を作成できることが必要です。  同様に、オートメーション サーバーは、オートメーション クライアントからの要求に対して動的に項目を作成できることが必要です。  
  
 Microsoft Foundation Class ライブラリには、2 つの OLE 専用マクロが用意されています。  
  
### OLE オブジェクトの動的な作成  
  
|||  
|-|-|  
|[DECLARE\_OLECREATE](../Topic/DECLARE_OLECREATE.md)|OLE オートメーションによるオブジェクトの作成を可能にします。|  
|[IMPLEMENT\_OLECREATE](../Topic/IMPLEMENT_OLECREATE.md)|OLE システムによるオブジェクトの作成を可能にします。|  
  
## 参照  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)