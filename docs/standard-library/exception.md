---
title: "&lt;exception&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<exception>"
  - "std::<exception>"
  - "std.<exception>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception ヘッダー"
ms.assetid: 28900768-5dd7-4834-b907-5e37ab3407db
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;exception&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外の処理に関連する型と関数を定義します。 例外処理は、システムがエラーから回復できる場合に使用されます。 例外処理では、関数からプログラムへ制御を返すための方法を利用できます。 例外処理を組み込む目的は、規則的な手順でエラーから回復する方法を実施して、プログラムの信頼性を向上させることです。  
  
## <a name="syntax"></a>構文  
  
```  
#include <exception>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[exception_ptr](../Topic/%3Cexception%3E%20typedefs.md#exception_ptr)|例外へのポインターを表す型。|  
|[terminate_handler](../Topic/%3Cexception%3E%20typedefs.md#terminate_handler)|`terminate_handler` として使用するのに適した関数へのポインターを表す型。|  
|[unexpected_handler](../Topic/%3Cexception%3E%20typedefs.md#unexpected_handler)|`unexpected_handler` として使用するのに適した関数へのポインターを表す型。|  
  
### <a name="functions"></a>関数  
  
|||  
|-|-|  
|[current_exception](../Topic/%3Cexception%3E%20functions.md#current_exception)|現在の例外へのポインターを取得します。|  
|[get_terminate](../Topic/%3Cexception%3E%20functions.md#get_terminate)|現在の `terminate_handler` 関数を取得します。|  
|[get_unexpected](../Topic/%3Cexception%3E%20functions.md#get_unexpected)|現在の `unexpected_handler` 関数を取得します。|  
|[make_exception_ptr](../Topic/%3Cexception%3E%20functions.md#make_exception_ptr)|例外のコピーを保持する `exception_ptr` オブジェクトを作成します。|  
|[rethrow_exception](../Topic/%3Cexception%3E%20functions.md#rethrow_exception)|パラメーターとして渡された例外をスローします。|  
|[set_terminate](../Topic/%3Cexception%3E%20functions.md#set_terminate)|プログラムの終了時に呼び出される新しい `terminate_handler` を設定します。|  
|[set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected)|予期しない例外が発生したときに新しい `unexpected_handler` が存在するように設定します。|  
|[終了](../Topic/%3Cexception%3E%20functions.md#terminate)|終了ハンドラーを呼び出します。|  
|[uncaught_exception](../Topic/%3Cexception%3E%20functions.md#uncaught_exception)|返します。 **true** スローされた例外は、現在処理されている場合にのみです。|  
|[予期しません。](../Topic/%3Cexception%3E%20functions.md#unexpected)|予期しないハンドラーを呼び出します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[bad_exception クラス](../standard-library/bad-exception-class.md)|このクラスは、`unexpected_handler` からスローされる例外を記述します。|  
|[exception クラス](Exception%20Class.xml)|このクラスは、特定の式と標準 C++ ライブラリによってスローされたすべての例外の基底クラスとして機能します。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

