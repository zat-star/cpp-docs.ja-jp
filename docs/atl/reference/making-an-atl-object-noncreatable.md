---
title: "ATL オブジェクトを作成できないを行う |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vc.appwiz.ATL.objects
dev_langs: C++
helpviewer_keywords:
- noncreatable ATL objects
- ATL projects, noncreatable objects
ms.assetid: 80d0bca2-dea0-4801-9a85-6243124437f6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e0e37779b081de457782ee59324a00cca5fedaea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="making-an-atl-object-noncreatable"></a>ATL オブジェクトを作成できないを行う
クライアントは、オブジェクトを直接作成できないように ATL ベースの COM オブジェクトの属性を変更することができます。 ここでは、オブジェクトとする別のオブジェクトのメソッド呼び出しによって返されるではなく直接作成します。  
  
### <a name="to-make-an-object-noncreatable"></a>オブジェクトを作成できないようにするには  
  
1.  削除、 [OBJECT_ENTRY_AUTO](object-map-macros.md#object_entry_auto)オブジェクト。 Noncreatable が登録するコントロールであるオブジェクトを実行する場合に、置換の OBJECT_ENTRY_AUTO[役立つ](object-map-macros.md#object_entry_non_createable_ex_auto)です。  
  
2.  追加、 [noncreatable](../../windows/noncreatable.md) .idl ファイルのコクラスの属性です。 例:  
  
 ```  
 [  
    uuid(A1992E3D-3CF0-11D0-826F-00A0C90F2851), 
    helpstring("MyObject"), 
    noncreatable]  
    coclass MyObject  
 {  
 [default] interface IMyInterface;  
 }  
 ```  
  
## <a name="see-also"></a>参照  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基本事項](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)

