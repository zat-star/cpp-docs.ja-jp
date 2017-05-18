---
title: "COM + 1.0 では、ATL COM + 1.0 コンポーネント ウィザード |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- vc.codewiz.class.atl.mts.options
dev_langs:
- C++
ms.assetid: 2fbe259c-6be1-4d0e-9cfe-721c75c97cb1
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 36295e5ce296ea6ba982c4ce8cf729bf45860883
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="com-10-atl-com-10-component-wizard"></a>COM+ 1.0、ATL COM+ 1.0 コンポーネント ウィザード
ATL COM + 1.0 コンポーネント ウィザードのこのページを使用すると、サポートされるように、インターフェイスの種類とその他のインターフェイスを指定できます。  
  
 ATL プロジェクトと ATL COM クラスの詳細については、次を参照してください。 [ATL COM デスクトップ コンポーネント](../../atl/atl-com-desktop-components.md)します。  
  
 **インターフェイス**  
 オブジェクトがサポートするインターフェイスの種類を示します。 既定では、オブジェクトには、デュアル インターフェイスがサポートしています。  
  
|オプション|説明|  
|------------|-----------------|  
|**デュアル**|オブジェクトがデュアル インターフェイスをサポートするように指定 (その vtable がカスタム インターフェイス関数と遅延バインディング`IDispatch`メソッド)。 COM クライアントとオートメーション コント ローラーがオブジェクトへのアクセスを許可します。|  
|**カスタム**|オブジェクトが (その vtable は、カスタム インターフェイス機能を持つ) カスタム インターフェイスをサポートするように指定します。 カスタム インターフェイスはプロセス境界をまたいで特にデュアル インターフェイスよりも高速化できます。<br /><br /> -   **オートメーションとの互換性**カスタム インターフェイスにオートメーションによるサポートを追加します。 属性付きプロジェクトでは、設定、 **oleautomation**コクラスの属性です。|  
  
 **Queueable**  
 クライアントが非同期的にメッセージ キューを使用して、このコンポーネントを呼び出せることを示します。 .H ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) には、属性付きコンポーネント マクロ カスタム (TLBATTR_QUEUEABLE 0) を追加します。  
  
 **サポート**  
 エラーの処理とオブジェクトのコントロールの追加サポートを示します。  
  
|オプション|説明|  
|------------|-----------------|  
|**ISupportErrorInfo**|サポートを作成、 [ISupportErrorInfo](../../atl/reference/isupporterrorinfoimpl-class.md)インターフェイスのため、オブジェクトは、クライアントにエラー情報を返すことができます。|  
|**IObjectControl**|3 つに、オブジェクトのアクセスを提供[IObjectControl](http://msdn.microsoft.com/library/windows/desktop/ms686474)メソッド: [Activate](http://msdn.microsoft.com/library/windows/desktop/ms681303)、 [CanBePooled](http://msdn.microsoft.com/library/windows/desktop/ms684322)、および[非アクティブ化](http://msdn.microsoft.com/library/windows/desktop/ms687094)します。|  
|**IObjectConstruct**|サポートを作成、 [IObjectConstruct](http://msdn.microsoft.com/library/windows/desktop/ms680583)他のメソッドやオブジェクトからパラメーターの受け渡しを管理するインターフェイスです。|  
  
 **トランザクション**  
 オブジェクトがトランザクションをサポートすることを示します。 .Idl ファイル (属性なしプロジェクト) には、ファイル mtxattr.h が含まれています。  
  
|オプション|説明|  
|------------|-----------------|  
|**サポートされています。**|オブジェクトが決してトランザクション ストリームのルートを .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_SUPPORTED,0) を追加することを指定します。|  
|**必須**|オブジェクトが場合がありますか、.h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQUIRED,0) を追加することによってトランザクション ストリームのルートができない可能性がありますを指定します。|  
|**サポートされていません**|オブジェクトがトランザクションを排除するように指定します。 .H ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_NOTSUPP,0) を追加します。|  
|**Requiresnew します。**|オブジェクトが常にトランザクション ストリームのルートである .h ファイル (属性付きプロジェクト) または .idl ファイル (属性なしプロジェクト) には、コンポーネントの属性マクロ custom(TLBATTR_TRANS_REQNEW,0) を追加することを指定します。|  
  
## <a name="see-also"></a>関連項目  
 [ATL COM + 1.0 コンポーネント ウィザード](../../atl/reference/atl-com-plus-1-0-component-wizard.md)   
 [ATL COM + 1.0 コンポーネント](../../atl/reference/adding-an-atl-com-plus-1-0-component.md)


