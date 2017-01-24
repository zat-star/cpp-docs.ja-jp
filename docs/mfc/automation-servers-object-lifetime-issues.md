---
title: "オートメーション サーバー : オブジェクトの生成と破棄 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "オートメーション サーバー, オブジェクトの有効期間"
  - "有効期間, オートメーション サーバー"
  - "オブジェクト [C++], 有効期間"
  - "サーバー, 有効期間 (オートメーションの)"
ms.assetid: 342baacf-4015-4a0e-be2f-321424f1cb43
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# オートメーション サーバー : オブジェクトの生成と破棄
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE アイテムは、オートメーション クライアントからを作成または操作すると、サーバーはそのオブジェクトにクライアントにポインターを渡します。  クライアントは、呼び出しによって OLE 関数 [IUnknown::AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)にオブジェクトへの参照を確立します。  この参照は、クライアントの呼び出し [IUnknown::Release](http://msdn.microsoft.com/library/windows/desktop/ms682317)まで有効です。\(Microsoft Foundation Class\) ライブラリの OLE クラスで作成されたクライアント アプリケーションは、これらの呼び出しを呼び出す必要はありません; フレームワークは、\)。OLE システムとサーバー自体はオブジェクトへの参照を確立する場合があります。  サーバーは、そのオブジェクトに対する外部参照の有効性を保持しているオブジェクトを破棄する必要があります。  
  
 フレームワークは [CCmdTarget](../Topic/CCmdTarget%20Class.md)から派生されるすべてのサーバー オブジェクトへの参照の数の内部カウントを保持します。  この数値は、オートメーション クライアントまたはそのほかのエンティティをオブジェクトへの参照を追加するか、離したときに更新されます。  
  
 参照カウントが 0 になると、フレームワークによって仮想 [CCmdTarget::OnFinalRelease](../Topic/CCmdTarget::OnFinalRelease.md)関数を呼び出します。  この関数の既定の実装からこのオブジェクトを削除する **delete** の演算子。  
  
 Microsoft Foundation Class ライブラリは制御のアプリケーションの動作に外部クライアントがアプリケーション オブジェクトへの参照がある場合に、追加の機能を提供します。  各オブジェクトへの参照の数を保持する以外に、サーバーはアクティブなオブジェクトのグローバルのカウントを保持します。  グローバル関数 [AfxOleLockApp](../Topic/AfxOleLockApp.md) と [AfxOleUnlockApp](../Topic/AfxOleUnlockApp.md)、実行中のアプリケーションのオブジェクトの数を更新します。  この数値に 0 以外のの場合、アプリケーションはユーザーがシステム メニューの閉じるまたはファイル メニューの終了をクリックすると終了しません。  代わりに、アプリケーションのメイン ウィンドウは、保留中のすべてのクライアント要求が完了するまでになります \(ただし、破棄されない\)。  通常、`AfxOleLockApp` と `AfxOleUnlockApp` はクラスのコンストラクターとデストラクターで、それぞれそのサポート オートメーション呼び出されます。  
  
 状況により、クライアントは、オブジェクトへの参照があるときに、サーバーに変換されます。  たとえば、サーバー リソースが依存する使用できなくなる可能性があるエラーを検出するためにサーバーを指定します。  ユーザーは、他のアプリケーションが参照するオブジェクトを含むサーバー ドキュメントを閉じることがあります。  
  
 [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)]で、`IUnknown::AddRef` と `IUnknown::Release`を参照してください。  
  
## 参照  
 [オートメーション サーバー](../mfc/automation-servers.md)   
 [AfxOleCanExitApp](../Topic/AfxOleCanExitApp.md)