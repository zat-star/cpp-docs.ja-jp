---
title: "パラメーターの検証 | Microsoft Docs"
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
  - "パラメーター, 検証"
ms.assetid: 019dd5f0-dc61-4d2e-b4e9-b66409ddf1f2
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# パラメーターの検証
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

セキュリティが強化された CRT 関数と既存の関数の多くのほとんどは、パラメーターを検証します。  これは、ポインターを null をチェックするか、整数が有効な範囲に把握することが、列挙値が有効であるかどうかを検証する必要がある場合があります。  無効なパラメーターがある場合、無効なパラメーター ハンドラーが実行されます。  
  
## 無効なパラメーター ハンドラー ルーチン  
 無効なパラメーターがある場合は C ランタイムの動作は現在割り当てられている無効なパラメーター ハンドラーを呼び出します。  既定の無効なパラメーターは、分析用の Microsoft のクラッシュ ダンプを読み込みするかをアプリケーションがクラッシュし、ユーザーを問い合わせるワトソン博士クラッシュのレポートを呼び出します。  デバッグ モードでは、無効なパラメーターは、アサーション エラーが発生します。  
  
 この動作は独自の関数は無効なパラメーター ハンドラーを設定するには [\_set\_invalid\_parameter\_handler \_set\_thread\_local\_invalid\_parameter\_handler](../c-runtime-library/reference/set-invalid-parameter-handler-set-thread-local-invalid-parameter-handler.md) 関数を使用して変更できます。  指定した関数がアプリケーションを終了して、コントロールが受け取った関数に無効なパラメーターは、これらの関数は正常に実行を指定された場合は、エラー コードにエラー コードを設定 `errno` を返します。  多くの場合、`errno` 値と戻り値に無効なパラメーターを示す両方 `EINVAL`です。  場合によっては、特定のエラー コードは、パラメーターとして渡された不正なファイル ポインターの `EBADF` など、返されます。  errno の詳細については、「[errno、\_doserrno、\_sys\_errlist、および \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md)」を参照してください。  
  
## 参照  
 [CRT のセキュリティ機能](../Topic/Security%20Features%20in%20the%20CRT.md)   
 [CRT ライブラリの機能](../c-runtime-library/crt-library-features.md)