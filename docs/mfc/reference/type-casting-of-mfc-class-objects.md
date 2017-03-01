---
title: "MFC クラス オブジェクトのキャストを入力 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros.classes
dev_langs:
- C++
helpviewer_keywords:
- macros, type casting
- pointers, type casting
- type casts
- casting types
- macros, casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
caps.latest.revision: 15
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f1ae094e7085017f03daab3f73323da13ab1be39
ms.lasthandoff: 02/24/2017

---
# <a name="type-casting-of-mfc-class-objects"></a>MFC クラス オブジェクトの型キャスト
型キャスト マクロは、キャストが有効なことを確認せず、特定のクラスのオブジェクトを指すポインターに指定されたポインターにキャストする方法を提供します。  
  
 次の表は、MFC 型のキャスト マクロを一覧表示します。  
  
### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>MFC クラス オブジェクトへのポインターにキャストするマクロ  
  
|||  
|-|-|  
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|キャストが有効かどうかを確認中に、クラス オブジェクトへのポインターへのポインターをキャストします。|  
|[STATIC_DOWNCAST](#static_downcast)|ポインターに関連する型の&1; つのクラスからオブジェクトへのポインターをキャストします。 デバッグ ビルドで、 **ASSERT**オブジェクトがない場合、ターゲットの種類"kind of""です。|  
  
##  <a name="a-namedynamicdowncasta--dynamicdowncast"></a><a name="dynamic_downcast"></a>DYNAMIC_DOWNCAST  
 キャストが有効かどうかを確認中に、クラスのオブジェクトへのポインターへのポインターをキャストする便利な方法を提供します。  
  
```   
DYNAMIC_DOWNCAST(class, pointer)  
```  
  
### <a name="parameters"></a>パラメーター  
 `class`  
 クラスの名前。  
  
 `pointer`  
 型のオブジェクトへのポインターにキャストするポインター`class`します。  
  
### <a name="remarks"></a>コメント  
 マクロがキャスト、`pointer`パラメーターのオブジェクトへのポインターを`class`パラメーターの型。  
  
 マウス ポインターによって参照されるオブジェクトがある場合、識別されたクラス"kind of""マクロは、適切なポインターを返します。 これがないかどうか、有効なキャスト、マクロを返します**NULL**します。  
  
##  <a name="a-namestaticdowncasta--staticdowncast"></a><a name="static_downcast"></a>STATIC_DOWNCAST  
 キャスト*pobject*へのポインターを*、それ以外*オブジェクトです。  
  
```   
STATIC_DOWNCAST(class_name, pobject)   
```  
  
### <a name="parameters"></a>パラメーター  
 *それ以外*  
 キャストされているクラスの名前。  
  
 *pobject*  
 ポインターにキャストへのポインター、 *、それ以外*オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 *pobject*配置するか、 **NULL**、オブジェクトを直接派生クラスのまたはから間接的に指すまたは*、それ以外*します。 使用してアプリケーションのビルドでは、 **_DEBUG**プリプロセッサ シンボルを定義すると、マクロは**ASSERT**場合*pobject*は**NULL**はないオブジェクトを指している場合、またはで指定されたクラス"kind of""、 *、それ以外*パラメーター (を参照してください[使うため](../../mfc/reference/cobject-class.md#iskindof))。 以外の**_DEBUG**ビルド マクロは、型チェックなしのキャストを実行します。  
  
 指定されたクラス、 *、それ以外*からパラメーターを派生させる必要があります`CObject`を使用してください、`DECLARE_DYNAMIC`と`IMPLEMENT_DYNAMIC`、`DECLARE_DYNCREATE`と`IMPLEMENT_DYNCREATE`、または`DECLARE_SERIAL`と`IMPLEMENT_SERIAL`マクロの記事で説明したよう[CObject クラス: CObject からクラスを派生する](../../mfc/deriving-a-class-from-cobject.md)です。  
  
 ポインターをキャストするなど、`CMyDoc`という`pMyDoc`へのポインターに**CDocument**この式を使用します。  
  
 [!code-cpp[NVC_MFCDocView #&197;](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]  
  
 場合`pMyDoc`から直接または間接的に派生したオブジェクトを指していない**CDocument**、マクロは**ASSERT**します。  
  
## <a name="see-also"></a>関連項目  
 [マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)

