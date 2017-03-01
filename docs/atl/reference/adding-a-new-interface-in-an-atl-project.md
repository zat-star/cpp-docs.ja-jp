---
title: "ATL プロジェクトに新しいインターフェイスの追加 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: 8e4916c60310dd8dcbf0bb9e8c1f151309a32621
ms.lasthandoff: 02/24/2017

---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL プロジェクトに新しいインターフェイスを追加します。
オブジェクトまたはコントロールにインターフェイスを追加する場合は、そのインターフェイスで各メソッドのスタブ関数を作成します。 オブジェクトやコントロールでは、既存のタイプ ライブラリ内にあるインターフェイスだけを追加できます。 また、インターフェイスを追加するクラスを実装する必要があります、 [BEGIN_COM_MAP](http://msdn.microsoft.com/library/ead2a1e3-334d-44ad-bb1f-b94bb14c2333)マクロ場合は、プロジェクトに属性が必要か、`coclass`属性です。  
  
 2 つの方法のいずれかのコントロールに新しいインターフェイスを追加することができます: 手動でまたはクラス ビューで、コード ウィザードを使用します。  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>クラス ビューでコード ウィザードを使用して、既存のオブジェクトまたはコントロールにインターフェイスを追加するには  
  
1.  [クラス ビュー](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)コントロールのクラス名を右クリックします。 たとえば、フル コントロールまたは複合コントロール、またはヘッダー ファイルで、BEGIN_COM_MAP マクロを実装するその他のコントロール クラスにします。  
  
2.  ショートカット メニューをクリックして**追加**、クリックして**インターフェイスの実装**します。  
  
3.  実装するインターフェイスを選択して、[インターフェイス実装ウィザード](../../ide/implement-interface-wizard.md)します。 インターフェイスが使用可能なタイプ ライブラリ内にない場合、必要があります、手動で追加する .idl ファイルにします。  
  
### <a name="to-add-a-new-interface-manually"></a>新しいインターフェイスを手動で追加するには  
  
1.  .Idl ファイルに新しいインターフェイスの定義を追加します。  
  
2.  オブジェクトまたはインターフェイスからコントロールを派生します。  
  
3.  新しい[COM_INTERFACE_ENTRY](http://msdn.microsoft.com/library/c5363b8b-a1a2-471e-ad3a-d472f6c356c5)インターフェイスの場合、プロジェクトに属性が追加、`coclass`属性です。  
  
4.  インターフェイスにメソッドを実装します。  
  
## <a name="see-also"></a>関連項目  
 [ATL プロジェクト ウィザード](../../atl/reference/atl-project-wizard.md)   
 [Visual C プロジェクトの種類](../../ide/visual-cpp-project-types.md)   
 [アプリケーション ウィザードを使用して、デスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL および C ランタイム コードによるプログラミング](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM オブジェクトの基礎](../../atl/fundamentals-of-atl-com-objects.md)   
 [ATL プロジェクトの既定の構成](../../atl/reference/default-atl-project-configurations.md)


