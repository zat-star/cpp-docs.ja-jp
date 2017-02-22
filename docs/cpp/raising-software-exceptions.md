---
title: "ソフトウェア例外の発生 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "エラー [C++], 例外として処理"
  - "例外処理, エラーの検出"
  - "例外処理, エラー (例外として)"
  - "例外, エラーのフラグ付け (例外として)"
  - "例外, ソフトウェア"
  - "書式 [C++], 例外コード"
  - "RaiseException 関数"
  - "ランタイム エラー, 例外として処理"
  - "ソフトウェア例外"
  - "構造化例外処理, エラー (例外として)"
ms.assetid: be1376c3-c46a-4f52-ad1d-c2362840746a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ソフトウェア例外の発生
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

プログラム エラーの最も一般的な原因のいくつかは、システムによって例外としてフラグが設定されません。  たとえば、メモリ ブロックを割り当てるときにメモリが不足していると、ランタイム関数または API 関数で例外は発生しませんが、エラー コードが返されます。  
  
 ただし、コードの条件を検出し、[RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) 関数を呼び出してその条件を報告することで、条件を例外として処理できます。  この方法でエラーにフラグを設定すれば、構造化例外処理の長所をあらゆるランタイム エラーに取り込むことができます。  
  
 エラーで構造化例外処理を使用するには、次の手順に従います。  
  
-   イベントごとに例外コードを定義します。  
  
-   問題を検出した時点で **RaiseException** を呼び出します。  
  
-   例外処理フィルターを使用して、定義した例外コードをテストします。  
  
 WINERROR.H ファイルは例外コードの形式を示します。  既存の例外コードと競合するコードを定義しないように、第 3 上位ビットを 1 に設定します。  4 つの最上位ビットは、次の表に示すように設定する必要があります。  
  
|ビット|推奨バイナリ設定|説明|  
|---------|--------------|--------|  
|31\-30|11|これら 2 つのビットは、コードの基本的なステータスを示します \(11 \= エラー、00 \= 成功、01 \= 情報、10 \= 警告\)。|  
|29|1|クライアント ビット。  ユーザー定義コードの場合は 1 に設定します。|  
|28|0|予約済みのビット  \(0 に設定しておきます\)。|  
  
 必要であれば、最初の 2 ビットをバイナリ 11 以外に設定できますが、通常はほとんどの例外に "エラー" を設定します。  注意すべき重要事項は、前の表に示すようにビット 29 と 28 を設定することです。  
  
 したがって、結果のエラー コードは 16 進数の E に設定された最上位の 4 ビットが必要です。  たとえば、次の例では、Windows 例外コードと競合しない例外コードを定義しています  \(ただし、サード パーティの DLL がどのコードを使用するか確認する必要があります\)。  
  
```  
#define STATUS_INSUFFICIENT_MEM       0xE0000001  
#define STATUS_FILE_BAD_FORMAT        0xE0000002  
```  
  
 例外コードを定義したら、そのコードを使用して例外を発生させることができます。  たとえば、次のコードでは、メモリ割り当てエラーを検出すると STATUS\_INSUFFICIENT\_MEM 例外が発生します。  
  
```  
lpstr = _malloc( nBufferSize );  
if (lpstr == NULL)  
    RaiseException( STATUS_INSUFFICIENT_MEM, 0, 0, 0);  
```  
  
 例外を簡単に発生させるには、最後の 3 つのパラメーターを 0 に設定します。  最後の 3 つのパラメーターは、追加情報を渡し、ハンドラーの実行を中止するフラグを設定するときに使用します。  詳細については、[!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の [RaiseException](http://msdn.microsoft.com/library/windows/desktop/ms680552) 関数の説明を参照してください。  
  
 例外処理フィルターで、定義したコードをテストできます。  次に例を示します。  
  
```  
__try {  
    ...  
}  
__except (GetExceptionCode() == STATUS_INSUFFICIENT_MEM ||  
        GetExceptionCode() == STATUS_FILE_BAD_FORMAT )  
```  
  
## 参照  
 [例外ハンドラーの記述](../cpp/writing-an-exception-handler.md)   
 [構造化例外処理](../cpp/structured-exception-handling-c-cpp.md)