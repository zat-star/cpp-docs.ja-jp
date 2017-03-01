---
title: "CDocItem クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocItem
dev_langs:
- C++
helpviewer_keywords:
- items, document
- document items
- server documents, document items
- CDocItem class
- container document items
- client document items
- OLE documents, items
- server documents
ms.assetid: 84fb8610-a4c8-4211-adc0-e70e8d002c11
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 1ade88aa562180d5c3a6a7afe3fe26943a5d811d
ms.lasthandoff: 02/24/2017

---
# <a name="cdocitem-class"></a>CDocItem クラス
ドキュメント アイテムの基底クラスであり、ドキュメント データのコンポーネントです。  
  
## <a name="syntax"></a>構文  
  
```  
class CDocItem : public CCmdTarget  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CDocItem::GetDocument](#getdocument)|項目を含むドキュメントを返します。|  
|[CDocItem::IsBlank](#isblank)|アイテムが情報を格納しているかどうかを決定します。|  
  
## <a name="remarks"></a>コメント  
 `CDocItem`クライアントとサーバーの両方のドキュメントで OLE アイテムを表すオブジェクトが使用されます。  
  
 詳細については、記事を参照してください。[コンテナー: コンテナーの実装](../../mfc/containers-implementing-a-container.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CDocItem`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxole.h  
  
##  <a name="a-namegetdocumenta--cdocitemgetdocument"></a><a name="getdocument"></a>CDocItem::GetDocument  
 項目を含むドキュメントを取得するには、この関数を呼び出します。  
  
```  
CDocument* GetDocument() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムを保持するドキュメントへのポインター**NULL**アイテムがドキュメントの一部ではない場合。  
  
### <a name="remarks"></a>コメント  
 この関数は、派生クラスでオーバーライドされる[COleClientItem](../../mfc/reference/coleclientitem-class.md)と[実際](../../mfc/reference/coleserveritem-class.md)、いずれかにポインターを返す、 [COleDocument](../../mfc/reference/coledocument-class.md)、[直接](../../mfc/reference/colelinkingdoc-class.md)、または[COleServerDoc](../../mfc/reference/coleserverdoc-class.md)オブジェクトです。  
  
##  <a name="a-nameisblanka--cdocitemisblank"></a><a name="isblank"></a>CDocItem::IsBlank  
 既定のシリアル化が発生したときに、フレームワークによって呼び出されます。  
  
```  
virtual BOOL IsBlank() const;  
```  
  
### <a name="return-value"></a>戻り値  
 アイテムに情報が含まれていない場合は 0 以外。それ以外の場合 0 を返します。  
  
### <a name="remarks"></a>コメント  
 既定では、`CDocItem`オブジェクトは空ではありません。 [COleClientItem](../../mfc/reference/coleclientitem-class.md)から直接派生するため、オブジェクトに空白が場合があります`CDocItem`します。 ただし、[実際](../../mfc/reference/coleserveritem-class.md)オブジェクトが空では常にします。 既定では、OLE アプリケーションを含む`COleClientItem`x または y を持たないオブジェクトのエクステントがシリアル化します。 返すことによってこれは、 **TRUE**のオーバーライドから`IsBlank`ときに、項目を持たない x または y エクステントです。  
  
 シリアル化中に他のアクションを実装する場合は、この関数をオーバーライドします。  
  
## <a name="see-also"></a>関連項目  
 [CCmdTarget クラス](../../mfc/reference/ccmdtarget-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [COleDocument クラス](../../mfc/reference/coledocument-class.md)   
 [実際のクラス](../../mfc/reference/coleserveritem-class.md)   
 [COleClientItem クラス](../../mfc/reference/coleclientitem-class.md)

