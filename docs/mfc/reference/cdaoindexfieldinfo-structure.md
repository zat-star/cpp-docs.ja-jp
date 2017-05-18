---
title: "CDaoIndexFieldInfo 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 975b3a704936adc9d4205938bb2c757ab650f0d9
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 構造体
`CDaoIndexFieldInfo`構造体には、データ アクセス オブジェクト (DAO) に対して定義されているインデックス フィールド オブジェクトに関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
 `m_strName`  
 インデックスのフィールド オブジェクトの一意名します。 詳細については、DAO ヘルプの「名前プロパティ」を参照してください。  
  
 *m_bDescending*  
 Index オブジェクトによって定義されたインデックスの順序を示します。 **TRUE**場合は、順序は降順です。  
  
## <a name="remarks"></a>コメント  
 Index オブジェクトさまざまなフィールド、テーブル定義 (またはテーブルに基づくレコード セット) がでインデックス付けされたフィールドを示すことができます。 上のプライマリへの参照で情報を返す方法を示す、`m_pFieldInfos`のメンバー、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)を呼び出して取得したオブジェクト、`GetIndexInfo`クラスのメンバー関数[どちら](../../mfc/reference/cdaotabledef-class.md#getindexinfo)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)。  
  
 Index オブジェクトとインデックス フィールド オブジェクトは、MFC クラスでは表されません。 DAO オブジェクト クラスの基になる MFC オブジェクトの代わりに、[どちら](../../mfc/reference/cdaotabledef-class.md)または[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)インデックス コレクションと呼ばれるインデックス オブジェクトのコレクションが含まれています。 さらに、各インデックス オブジェクトには、フィールド オブジェクトのコレクションが含まれています。 これらのクラスを指定のインデックスについては、個々 の項目にアクセスするメンバー関数またはで一度にすべてにアクセスすることができます、`CDaoIndexInfo`オブジェクトを呼び出して、`GetIndexInfo`親オブジェクトのメンバー関数。 `CDaoIndexInfo`オブジェクト、その後、データ メンバーを持つ`m_pFieldInfos`の配列を指す`CDaoIndexFieldInfo`オブジェクトです。  
  
 呼び出す、`GetIndexInfo`インデックスでコレクションが含まれるテーブル定義またはレコード セット オブジェクトのメンバー関数は、興味のあるインデックス オブジェクトを格納します。 アクセスし、`m_pFieldInfos`のメンバー、 [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md)オブジェクトです。 長さ、`m_pFieldInfos`で配列が格納されている`m_nFields`します。 `CDaoIndexFieldInfo`定義して、`Dump`デバッグでのメンバー関数を作成します。 使用することができます`Dump`の内容をダンプする`CDaoIndexFieldInfo`オブジェクトです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdao.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)


