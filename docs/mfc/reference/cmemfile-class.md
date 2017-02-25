---
title: "CMemFile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMemFile クラス"
  - "メモリ ファイル"
  - "一時ファイル, メモリ ファイル"
ms.assetid: 20e86515-e465-4f73-b2ea-e49789d63165
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMemFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\- [CFile](../../mfc/reference/cfile-class.md)その派生クラスはメモリ上のファイルをサポートします。  
  
## 構文  
  
```  
class CMemFile : public CFile  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMemFile::CMemFile](../Topic/CMemFile::CMemFile.md)|メモリのファイル オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMemFile::Attach](../Topic/CMemFile::Attach.md)|`CMemFile`にメモリ ブロックを割り当てます。|  
|[CMemFile::Detach](../Topic/CMemFile::Detach.md)|`CMemFile` からメモリ ブロックをデタッチし、デタッチされたメモリ ブロックへのポインターを返します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMemFile::Alloc](../Topic/CMemFile::Alloc.md)|メモリ割り当ての動作を変更するためにオーバーライドします。|  
|[CMemFile::Free](../Topic/CMemFile::Free.md)|メモリの解放の動作を変更するためにオーバーライドします。|  
|[CMemFile::GrowFile](../Topic/CMemFile::GrowFile.md)|ファイルがない場合の動作を変更するためにオーバーライドします。|  
|[CMemFile::Memcpy](../Topic/CMemFile::Memcpy.md)|ファイルを読み書きするときにメモリのコピーの動作を変更するためにオーバーライドします。|  
|[CMemFile::Realloc](../Topic/CMemFile::Realloc.md)|メモリの再割り当ての動作を変更するためにオーバーライドします。|  
  
## 解説  
 これらのメモリ ファイルをディスク ファイルなどですが、ファイルがディスク上ではなく、RAM に格納されます。  メモリのファイルは、一時的なストレージまたは独立したプロセス間での生バイトまたはシリアル化されたオブジェクトを転送する場合に便利です。  
  
 `CMemFile` のオブジェクトは自動的に独自のメモリを割り当てるか、または `CMemFile` のオブジェクトに [&#91;アタッチ&#93;](../Topic/CMemFile::Attach.md)を呼び出すことにより、独自のメモリ ブロックを添付できます。  いずれの場合も、メモリ ファイルを拡張するメモリのサイズは `nGrowBytes`のインクリメントで自動的に `nGrowBytes` がゼロである割り当てられます。  
  
 メモリ ブロックは `CMemFile` のオブジェクトの破棄に自動的にメモリが `CMemFile` のオブジェクトによって最初に割り当てられている場合は削除されます; は、オブジェクトにアタッチしたメモリを解放する必要があります。  
  
 [&#91;デタッチ&#93;](../Topic/CMemFile::Detach.md)を呼び出して `CMemFile` のオブジェクトからそれをデタッチするときに指定されるポインターを通じてメモリ ブロックにアクセスできます。  
  
 `CMemFile` のは一般的に、`CMemFile` のオブジェクトを作成し、[CFile](../../mfc/reference/cfile-class.md) のメンバー関数を呼び出すことによって使用することです。  `CMemFile` を作成する自動的に開きますこのプロパティを処理します: ディスク ファイルにのみ使用して [CFile::Open](../Topic/CFile::Open.md)を呼び出していません。  `CMemFile` をディスク ファイルを使用しないため、データ メンバー `CFile::m_hFile` を使うことも意味がありません。  
  
 `CFile` のメンバー関数 [&#91;複製&#93;](../Topic/CFile::Duplicate.md)、[LockRange](../Topic/CFile::LockRange.md)と [UnlockRange](../Topic/CFile::UnlockRange.md) は `CMemFile`用に実装されていません。  `CMemFile` オブジェクトでこれらの関数を呼び出すと、[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md) になります。  
  
 `CMemFile` はメモリの割り当ておよび再割り当ておよび解放するためにランタイム ライブラリ関数 [malloc](../../c-runtime-library/reference/malloc.md)、[realloc](../../c-runtime-library/reference/realloc.md)と [free](../../c-runtime-library/reference/free.md) を使用して; を読み書きする場合のコピーのメモリ ブロックを組み込み [memcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md)。  `CMemFile` がファイルがない場合は、この動作と動作を変更するする場合は、独自のクラスを `CMemFile` から派生し、適切な関数をオーバーライドします。  
  
 `CMemFile`の詳細については、" " [MFC のファイル](../../mfc/files-in-mfc.md) と [メモリ管理 \(MFC\)](../../mfc/memory-management.md) を表示し、" *ランタイム ライブラリ リファレンス"の*[ファイルの処理](../../c-runtime-library/file-handling.md) を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CMemFile`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [CFile クラス](../../mfc/reference/cfile-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)