---
title: "プログラムによる印刷 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "アクティブ ドキュメント [C++], 印刷"
  - "IPrint インターフェイス"
  - "印刷 [MFC]"
  - "印刷 [MFC], アクティブ ドキュメント"
  - "印刷 [MFC], プログラムによる"
ms.assetid: 3db0945b-5e13-4be4-86a0-6aecdae565bd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# プログラムによる印刷
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE 方法を永続的なドキュメント \(**GetClassFile**\) を識別し、関連するコード \(`CoCreateInstance`、**QueryInterface\(IID\_IPersistFile\)**、**QueryInterface\(IID\_IPersistStorage\)**、**IPersistFile::Load**と **IPersistStorage::Load**\) に読み込むために使用します。  さらに印刷のドキュメントを有効にするには、アクティブ ドキュメントのコンテインメントは \(OLE 2.0 に最初に付属していない既存の OLE デザインを使用して\) ベース標準印刷インターフェイス、`IPrint`、一般に利用可能な状態をドキュメント タイプの永続的な状態を読み込むことができる任意のオブジェクトです。  アクティブ ドキュメントの各ビューには、オプションでこれらの機能を提供する **IPrint** インターフェイスをサポートします。  
  
 `IPrint` インターフェイスは次のように定義されます。:  
  
 `interface IPrint : IUnknown`  
  
 `{`  
  
 `HRESULT SetInitialPageNum([in] LONG nFirstPage);`  
  
 `HRESULT GetPageInfo(`  
  
 `[out] LONG *pnFirstPage,`  
  
 `[out] LONG *pcPages);`  
  
 `HRESULT Print(`  
  
 `[in] DWORD grfFlags,`  
  
 `[in,out] DVTARGETDEVICE **pptd,`  
  
 `[in,out] PAGESET ** ppPageSet,`  
  
 `[in,out] STGMEDIUM **ppstgmOptions,`  
  
 `[in] IContinueCallback* pCallback,`  
  
 `[in] LONG nFirstPage,`  
  
 `[out] LONG *pcPagesPrinted,`  
  
 `[out] LONG *pnPageLast);`  
  
 `};`  
  
 印刷する印刷の制御フラグは、ターゲット デバイス指定する、ドキュメント ページが読み込まれること自体を一度印刷するようにドキュメントに指示するクライアントと単にコンテナーを使用 **IPrint::Print** と追加オプション。  クライアントは、インターフェイス `IContinueCallback` \(以下を参照\) で印刷の継続を制御できます。  
  
 また、 **IPrint::SetInitialPageNum**、明らかにアクティブ ドキュメント コンテナーの利点 Office バインダーを使用するページにシームレスに番号を追加して 1 つがと同時に複数のドキュメントを印刷できます。  **IPrint::GetPageInfo** に より、改ページ情報を呼び出し元の前に **SetInitialPageNum** \(またはページ番号を開始するための内部既定\) に渡される開始ページ番号とドキュメントのページ数を取得するため、簡単に表示されます。  
  
 `IPrint` をサポートするオブジェクトは、オブジェクトの CLSID に格納されている「印刷可能な」キーのレジストリでマークする:  
  
 HKEY\_CLASSES\_ROOT\\CLSID\\{...}\\Printable  
  
 `IPrint` は 通常 `IPersistFile` または `IPersistStorage`をサポートする同じオブジェクトに実装されます。  呼び出し元は、プログラムでレジストリに印刷する機能に「印刷可能な」キーを表示することによって、クラスの永続的な状態を確認します。  現在、「印刷可能な」少なくとも `IPrint`のサポートを示します; **IPrint** がサポートの基本レベルを表す `QueryInterface` で使用できるそのほかのインターフェイスは、将来定義される可能性があります。  
  
 印刷プロシージャ中、印刷を続ける必要があるかどうかを制御するための印刷を開始したコンテナーまたはクライアントが必要になる場合があります。  たとえば、コンテナーは、印刷ジョブをできるだけ早く終了する必要がある「停止」印刷コマンドをサポートする場合があります。  この機能をサポートするには、印刷できるオブジェクトのクライアントは `IContinueCallback`インターフェイスを使用して、通知シンク オブジェクトを実装する:  
  
 `interface IContinueCallback : IUnknown`  
  
 `{`  
  
 `HRESULT FContinue(void);`  
  
 `HRESULT FContinuePrinting(`  
  
 `[in] LONG cPagesPrinted,`  
  
 `[in] LONG nCurrentPage,`  
  
 `[in] LPOLESTR pszPrintStatus);`  
  
 `};`  
  
 このインターフェイスは、Win32 API のさまざまな継続プロシージャの場所を使用する一般的な継続のコールバック関数として使用できるように設計されています \(印刷の **AbortProc** および Metafile クラスの列挙体の **EnumMetafileProc** など\)。  このインターフェイスには、時間のかかるプロセスに役立ちます。  
  
 最も一般的なケースでは、**IContinueCallback::FContinue** 関数は、長いプロセスによって定期的に呼び出されます。  シンク オブジェクトはプロシージャをできるだけ早く停止し、操作を継続する `S_OK` と **S\_FALSE** を返します。  
  
 ただし、**FContinue**は **IPrint::Print**のコンテキストで使用できません; 代わりに、使用 **IContinueCallback::FContinuePrint**を出力します。  どの印刷オブジェクトは、定期的に印刷するページ数、印刷するページ数を選択してクライアントがユーザーに表示するか、印刷がある状態を記述する追加の文字列を渡す **FContinuePrinting** を呼び出す必要があります \(「5 19 "のページなど\)。  
  
## 参照  
 [Active ドキュメント コンテナー](../mfc/active-document-containers.md)