---
title: "CFile クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive クラス, 使用 (CFile で)"
  - "CFile クラス"
  - "ファイル [C++], クラス"
ms.assetid: b2eb5757-d499-4e67-b044-dd7d1abaa0f8
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CFile クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ファイルに関する MFC の基本クラスです。  
  
## 構文  
  
```  
class CFile : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CFile::CFile](../Topic/CFile::CFile.md)|パスまたはファイル ハンドルから `CFile` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CFile::Abort](../Topic/CFile::Abort.md)|警告やエラーを無視してファイルを閉じます。|  
|[CFile::Close](../Topic/CFile::Close.md)|ファイルを閉じ、オブジェクトを削除します。|  
|[CFile::Duplicate](../Topic/CFile::Duplicate.md)|ファイルの複製オブジェクトを構築します。|  
|[CFile::Flush](../Topic/CFile::Flush.md)|まだ書き込まれていない任意のデータをフラッシュします。|  
|[CFile::GetFileName](../Topic/CFile::GetFileName.md)|選択したファイルの名前を取得します。|  
|[CFile::GetFilePath](../Topic/CFile::GetFilePath.md)|選択したファイルの完全パスを取得します。|  
|[CFile::GetFileTitle](../Topic/CFile::GetFileTitle.md)|選択したファイルのタイトルを取得します。|  
|[CFile::GetLength](../Topic/CFile::GetLength.md)|ファイルの長さを取得します。|  
|[CFile::GetPosition](../Topic/CFile::GetPosition.md)|現在のファイル ポインターを取得します。|  
|[CFile::GetStatus](../Topic/CFile::GetStatus.md)|開いているファイル、または静的なバージョンの状態を取得し、指定されたファイル \(静的関数、仮想関数\) の状態取得します。|  
|[CFile::LockRange](../Topic/CFile::LockRange.md)|ファイルのバイト列をロックします。|  
|[CFile::Open](../Topic/CFile::Open.md)|エラー テスト オプションを指定してファイルを安全に開きます。|  
|[CFile::Read](../Topic/CFile::Read.md)|ファイルの現在の位置から \(バッファーを介さずに\) データを読み込みます。|  
|[CFile::Remove](../Topic/CFile::Remove.md)|指定したファイルを削除します \(静的関数\)。|  
|[CFile::Rename](../Topic/CFile::Rename.md)|指定したファイルの名前を変更します \(静的関数\)。|  
|[CFile::Seek](../Topic/CFile::Seek.md)|現在のファイル ポインターを移動します。|  
|[CFile::SeekToBegin](../Topic/CFile::SeekToBegin.md)|現在のファイル ポインターをファイルの先頭に移動します。|  
|[CFile::SeekToEnd](../Topic/CFile::SeekToEnd.md)|現在のファイル ポインターをファイルの最後に移動します。|  
|[CFile::SetFilePath](../Topic/CFile::SetFilePath.md)|選択したファイルの完全パスを設定します。|  
|[CFile::SetLength](../Topic/CFile::SetLength.md)|ファイルの長さを変更します。|  
|[CFile::SetStatus](../Topic/CFile::SetStatus.md)|指定したファイルのステータスを設定します \(静的関数、仮想関数\)。|  
|[CFile::UnlockRange](../Topic/CFile::UnlockRange.md)|ファイルのバイト列のロックを解除します。|  
|[CFile::Write](../Topic/CFile::Write.md)|ファイルの現在の位置に \(バッファーを介さずに\) データを書き込みます。|  
  
### パブリック演算子  
  
|名前|説明|  
|--------|--------|  
|[CFile::operator HANDLE](../Topic/CFile::operator%20HANDLE.md)|`CFile` オブジェクトのハンドルを指定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFile::hFileNull](../Topic/CFile::hFileNull.md)|`CFile` オブジェクトに有効なハンドルがあるかどうかを判断します。|  
|[CFile::m\_hFile](../Topic/CFile::m_hFile.md)|通常、オペレーティング システム ファイルのハンドルを保持します。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CFile::m\_pTM](../Topic/CFile::m_pTM.md)|`CAtlTransactionManager` オブジェクトへのポインター。|  
  
## 解説  
 バッファリングされないバイナリ ディスクの入出力サービスを直接提供し、派生クラスを通じてテキスト ファイルとメモリ ファイルを間接的にサポートします。  `CFile` は、`CArchive` クラスと連携して動作して、Microsoft Foundation Class オブジェクトのシリアル化をサポートします。  
  
 このクラスとその派生クラスの間には階層的な関係があるため、ポリモーフィックな `CFile` インターフェイスを介して、すべてのファイル オブジェクトを操作できます。  たとえば、メモリ ファイルをディスク ファイルのように扱うことができます。  
  
 一般的なディスクの入出力には、`CFile` クラスとその派生クラスを使用します。  書式化されたテキストをディスク ファイルに送るには、`ofstream` またはその他の Microsoft iostream クラスを使用します。  
  
 通常、ディスク ファイルは `CFile` の構築時に自動的に開かれ、破棄時に閉じられます。  静的なメンバー関数を使うと、ファイルを開かずに、そのファイルのステータスを問い合わせることができます。  
  
 `CFile` の使い方の詳細については、『ランタイム ライブラリ リファレンス』の「[MFC のファイル](../../mfc/files-in-mfc.md)」および「[ファイル処理](../../c-runtime-library/file-handling.md)」を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CFile`  
  
## 必要条件  
 **ヘッダー:** afx.h  
  
## 参照  
 [MFC の DRAWCLI サンプル](../../top/visual-cpp-samples.md)   
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CStdioFile クラス](../Topic/CStdioFile%20Class.md)   
 [CMemFile クラス](../../mfc/reference/cmemfile-class.md)   
 [操作方法: CFile クラスを使用します。](http://go.microsoft.com/fwlink/?LinkId=128046)