---
title: "CLongBinary クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- BLOB
- CLongBinary
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: bb73604ee4d15f3a71be8514f348ad265064928a
ms.lasthandoff: 02/24/2017

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
|[CLongBinary::m_dwDataLength](#m_dwdatalength)|実際にそのハンドルが格納されているデータ オブジェクトのバイト サイズを格納`m_hData`します。|  
|[CLongBinary::m_hData](#m_hdata)|Windows を含む`HGLOBAL`実際のイメージ オブジェクトのハンドルします。|  
  
## <a name="remarks"></a>コメント  
 たとえば、SQL テーブル内のレコード フィールドには、画像のビットマップが含まれます。 A`CLongBinary`オブジェクトがこのようなオブジェクトを格納およびのサイズを追跡します。  
  
> [!NOTE]
>  一般に、使用するより良いことを今すぐは[CByteArray](../../mfc/reference/cbytearray-class.md)と組み合わせて、 [DFX_Binary](http://msdn.microsoft.com/library/678021a3-2e46-44d7-8528-71bb692dcc07)関数です。 引き続き使用できます`CLongBinary`が一般に、`CByteArray`は、win32 でより多くの機能がいないためサイズの制限が発生し、16 ビット`CByteArray`します。 このアドバイスは、データ アクセス オブジェクト (DAO) とオープン データベース コネクティビティ (ODBC) を使用したプログラミングに適用されます。  
  
 使用する、`CLongBinary`オブジェクト、型のフィールド データ メンバーを宣言`CLongBinary`レコード セット クラスにします。 このメンバーは、レコード セット クラスの埋め込みメンバーになり、レコード セットを作成するときに作成します。 後に、`CLongBinary`オブジェクトを構築する場合、レコード フィールド エクス (チェンジ RFX) メカニズムは、データ ソースの現在のレコードのフィールドからのデータ オブジェクトを読み込みますレコードが更新されたときに、レコードに格納します。 Rfx 関数では、バイナリ ラージ オブジェクトのサイズでは、ストレージを割り当て、そのに対するデータ ソースがクエリ実行 (を使用して、`CLongBinary`オブジェクトの`m_hData`データ メンバー)、し、格納、`HGLOBAL`内のデータへのハンドル`m_hData`します。 RFX も内のデータ オブジェクトの実際のサイズを格納、`m_dwDataLength`データ メンバーです。 によってオブジェクトのデータの操作`m_hData`、Windows に格納されているデータの操作に通常使用と同じ手法を使用して`HGLOBAL`を処理します。  
  
 埋め込まれているレコード セットを破棄する`CLongBinary`オブジェクトが破棄されるもと、デストラクターの割り当てを解除、`HGLOBAL`データ ハンドル。  
  
 ラージ オブジェクトとの使用の詳細については`CLongBinary`、記事を参照して[レコード セット (ODBC)](../../data/odbc/recordset-odbc.md)と[レコード セット: 大規模なデータ項目 (ODBC) での作業](../../data/odbc/recordset-working-with-large-data-items-odbc.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CLongBinary`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxdb_.h  
  
##  <a name="a-nameclongbinarya--clongbinaryclongbinary"></a><a name="clongbinary"></a>CLongBinary::CLongBinary  
 `CLongBinary` オブジェクトを構築します。  
  
```  
CLongBinary();
```  
  
##  <a name="a-namemdwdatalengtha--clongbinarymdwdatalength"></a><a name="m_dwdatalength"></a>CLongBinary::m_dwDataLength  
 格納されたデータのバイト単位の実際のサイズを格納、`HGLOBAL`で処理`m_hData`します。  
  
```  
SQLULEN m_dwDataLength;  
```  
  
### <a name="remarks"></a>コメント  
 このサイズは、データに割り当てられたメモリ ブロックのサイズより小さくすることがあります。 Win32 を呼び出す[GLobalSize](http://msdn.microsoft.com/library/windows/desktop/aa366593)割り当てサイズを取得します。  
  
##  <a name="a-namemhdataa--clongbinarymhdata"></a><a name="m_hdata"></a>CLongBinary::m_hData  
 Windows の格納`HGLOBAL`実際のバイナリ ラージ オブジェクト データを処理します。  
  
```  
HGLOBAL m_hData;  
```  
  
## <a name="see-also"></a>関連項目  
 [CObject クラス](../../mfc/reference/cobject-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRecordset クラス](../../mfc/reference/crecordset-class.md)

