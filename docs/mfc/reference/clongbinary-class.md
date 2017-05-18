---
title: "CLongBinary クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
dev_langs:
- C++
helpviewer_keywords:
- BLOB (binary large object)
- CLongBinary class
- BLOB (binary large object), CLongBinary class
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
caps.latest.revision: 21
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
ms.sourcegitcommit: d2d39abf526a58b8442107b5ee816f316ae841f5
ms.openlocfilehash: 4f06c6ef0b988a348f074d50ce7a33e8015a20fe
ms.contentlocale: ja-jp
ms.lasthandoff: 03/31/2017

---
# <a name="clongbinary-class"></a>CLongBinary クラス
データベース上の大きなバイナリ データ オブジェクト (BLOB または "バイナリ ラージ オブジェクト" と呼びます) を使った作業を単純にします。  
  
## <a name="syntax"></a>構文  
  
```  
class CLongBinary : public CObject  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CLongBinary::CLongBinary](#clongbinary)|`CLongBinary` オブジェクトを構築します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|ハンドルに保存されたデータ オブジェクトのバイト単位の実際のサイズを含む`m_hData`です。|  
|[CLongBinary::m_hData](#m_hdata)|Windows を含む`HGLOBAL`実際の画像オブジェクトへのハンドルします。|  
  
## <a name="remarks"></a>コメント  
 たとえば、SQL テーブル内のレコード フィールドには、画像のビットマップが含まれます。 A`CLongBinary`オブジェクトは、このようなオブジェクトを格納し、そのサイズの追跡します。  
  
> [!NOTE]
>  一般に、お勧めここで使用する[CByteArray](../../mfc/reference/cbytearray-class.md)と組み合わせて、 [DFX_Binary](record-field-exchange-functions.md#dfx_binary)関数。 使用することもできます`CLongBinary`が、一般に`CByteArray`提供 win32 でより多くの機能が存在しないためサイズの制限が発生し、16 ビット`CByteArray`です。 このアドバイスは、データ アクセス オブジェクト (DAO) とオープン データベース コネクティビティ (ODBC) を使用したプログラミングに適用されます。  
  
 使用する、`CLongBinary`オブジェクト、型のフィールド データ メンバーを宣言`CLongBinary`レコード セット クラスでします。 このメンバーは、レコード セット クラスの埋め込みメンバーになります、レコード セットを作成するときに構築されます。 後に、`CLongBinary`オブジェクトが構築された場合、レコード フィールド エクス (チェンジ RFX) メカニズムは、データ ソースの現在のレコードのフィールドからのデータ オブジェクトを読み込みますレコードが更新されたときに、レコードに格納します。 バイナリ ラージ オブジェクトのサイズが記憶域を割り当ててに対するクエリ、データ ソースに RFX (を使用して、`CLongBinary`オブジェクトの`m_hData`データ メンバー)、し、格納、`HGLOBAL`内のデータへのハンドル`m_hData`です。 RFX も内のデータ オブジェクトの実際のサイズを格納、`m_dwDataLength`データ メンバーです。 を介してそのオブジェクトでデータを操作`m_hData`、通常、Windows に格納されているデータを操作で使用する同じ手法を使用して`HGLOBAL`処理します。  
  
 レコード セット、埋め込まれているを破棄する`CLongBinary`オブジェクトも破棄され、そのデストラクターの割り当てを解除、`HGLOBAL`データ ハンドル。  
  
 ラージ オブジェクトとの使用の詳細については`CLongBinary`、記事を参照して[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)と[レコード セット: 大規模なデータ項目 (ODBC) での作業](../../data/odbc/recordset-working-with-large-data-items-odbc.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb_.h  
  
##  <a name="clongbinary"></a>CLongBinary::CLongBinary  
 `CLongBinary` オブジェクトを構築します。  
  
```  
CLongBinary();
```  
  
##  <a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 格納されたデータのバイト単位の実際のサイズを格納、`HGLOBAL`で処理`m_hData`です。  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>コメント  
 このサイズは、データに割り当てられたメモリ ブロックのサイズより小さくなる可能性があります。 Win32 を呼び出す[GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593)割り当てサイズを取得します。  
  
##  <a name="m_hdata"></a>CLongBinary::m_hData  
 Windows の格納`HGLOBAL`の実際のバイナリ ラージ オブジェクト データを処理します。  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)

