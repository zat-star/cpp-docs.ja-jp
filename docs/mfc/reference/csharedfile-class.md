---
title: "多くの場合クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSharedFile
- AFXADV/CSharedFile
- AFXADV/CSharedFile::CSharedFile
- AFXADV/CSharedFile::Detach
- AFXADV/CSharedFile::SetHandle
dev_langs:
- C++
helpviewer_keywords:
- memory files
- CSharedFile class
- shared memory files
ms.assetid: 5d000422-9ede-4318-a8c9-f7412b674f39
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
ms.openlocfilehash: f812b2c7b8e3b158068bf3fdab0a327460056251
ms.lasthandoff: 02/24/2017

---
# <a name="csharedfile-class"></a>クラスの多くの場合
[CMemFile](../../mfc/reference/cmemfile-class.md)-をサポートする派生クラスは、メモリ上のファイルを共有します。  
  
## <a name="syntax"></a>構文  
  
```  
class CSharedFile : public CMemFile  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[CSharedFile::CSharedFile](#csharedfile)|`CSharedFile` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CSharedFile::Detach](#detach)|共有メモリ ファイルを閉じ、そのメモリ ブロックのハンドルを返します。|  
|[CSharedFile::SetHandle](#sethandle)|メモリ ブロックへの共有メモリ ファイルをアタッチします。|  
  
## <a name="remarks"></a>コメント  
 メモリ ファイルは、ファイルはディスクではなく RAM に保存する点を除いて、ディスク ファイルと同様に動作します。 メモリ ファイルは高速に一時的な記憶域または実際のバイト数を転送するために役立ちます。 または、独立したプロセス間でオブジェクトをシリアル化します。  
  
 共有メモリ ファイルとは異なり他のメモリ上のファイルでそれらのメモリが割り当てられた、 [GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574) Windows の機能です。 `CSharedFile`クラスは、グローバルに割り当てられたメモリ ブロックにデータを保存 (を使用して作成**GlobalAlloc**)、このメモリ ブロックを共有できる DDE、クリップボード、または、他の OLE と COM 汎用データ転送操作などを使用して使用して`IDataObject`です。  
  
 **GlobalAlloc**返します、`HGLOBAL`によって返されたポインターなどのメモリへのポインターではなく処理[malloc](../../c-runtime-library/reference/malloc.md)します。 `HGLOBAL`ハンドルは、特定のアプリケーションで必要です。 たとえば、データを保存、クリップボードする必要があります、`HGLOBAL`を処理します。  
  
 なお、`CSharedFile`使用メモリ マップ ファイルではなくを行い、プロセス間でデータを直接共有することはできません。  
  
 `CSharedFile`オブジェクトは、独自のメモリを自動的に割り当てることができますか、独自のメモリ ブロックを割り当てることができます、`CSharedFile`を呼び出してオブジェクト[CSharedFile::SetHandle](#sethandle)します。 いずれの場合メモリ ファイルを自動的に拡張用のメモリが割り当てられている`nGrowBytes`-場合分ずつ`nGrowBytes`が&0; でないです。  
  
 詳細については、記事を参照してください。 [MFC のファイル](../../mfc/files-in-mfc.md)と[ファイル処理](../../c-runtime-library/file-handling.md)で、*ランタイム ライブラリ リファレンス*します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CMemFile](../../mfc/reference/cmemfile-class.md)  
  
 `CSharedFile`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** afxadv.h  
  
##  <a name="csharedfile"></a>CSharedFile::CSharedFile  
 構築、`CSharedFile`オブジェクトし、メモリを割り当てます。  
  
```  
CSharedFile(
    UINT nAllocFlags = GMEM_DDESHARE | GMEM_MOVEABLE,  
    UINT nGrowBytes = 4096);
```  
  
### <a name="parameters"></a>パラメーター  
 *nAllocFlags*  
 メモリの割り当て方法を示すフラグです。 参照してください[GlobalAlloc](http://msdn.microsoft.com/library/windows/desktop/aa366574)の有効なフラグ値の一覧です。  
  
 `nGrowBytes`  
 バイト単位でメモリ割り当てインクリメントします。  
  
##  <a name="detach"></a>CSharedFile::Detach  
 この関数では、ファイルを閉じて、メモリ、メモリ ブロックからデタッチします。  
  
```  
HGLOBAL Detach();
```  
  
### <a name="return-value"></a>戻り値  
 メモリ ファイルの内容を保持するメモリ ブロックのハンドル。  
  
### <a name="remarks"></a>コメント  
 呼び出して開くことができます[SetHandle](#sethandle)、によって返されるハンドルを使用して**デタッチ**します。  
  
##  <a name="sethandle"></a>CSharedFile::SetHandle  
 グローバル メモリ ブロックをアタッチするには、この関数を呼び出す、`CSharedFile`オブジェクトです。  
  
```  
void SetHandle(
    HGLOBAL hGlobalMemory,  
    BOOL bAllowGrow = TRUE);
```  
  
### <a name="parameters"></a>パラメーター  
 *hGlobalMemory*  
 アタッチされているグローバル メモリへのハンドル、`CSharedFile`です。  
  
 `bAllowGrow`  
 メモリ ブロックを拡張できるかどうかを指定します。  
  
### <a name="remarks"></a>コメント  
 場合`bAllowGrow`は&0; 以外の値、メモリ ブロックのサイズが増加、必要に応じてなどの場合は、試行が行われたファイルに書き込むバイト数、メモリ ブロックの割り当てられたよりもします。  
  
## <a name="see-also"></a>関連項目  
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)

