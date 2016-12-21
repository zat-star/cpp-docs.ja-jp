---
title: "C ランタイム エラー R6035 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "R6035"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "R6035"
ms.assetid: f8fb50b8-18bf-4258-b96a-b0a9de468d16
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C ランタイム エラー R6035
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Microsoft Visual C\+\+ ランタイム ライブラリ、エラー R6035 \- あるグローバル セキュリティ クッキーに依存している関数がアクティブになっている間に、このアプリケーション内のモジュールが、そのモジュールに所属するそのセキュリティ クッキーを初期化しました。\_\_security\_init\_cookie を既に呼び出しました。  
  
 [\_\_security\_init\_cookie](../../c-runtime-library/reference/security-init-cookie.md) は、グローバル セキュリティ クッキーを初めて使用する前に呼び出す必要があります。  
  
 グローバル セキュリティ クッキーは、[\/GS \(バッファーのセキュリティ チェック\)](../Topic/-GS%20\(Buffer%20Security%20Check\).md) を指定してコンパイルされたコードおよび構造化例外処理を使用するコードでバッファー オーバーランから保護するために使用されます。  基本的に、オーバーランから保護された関数を呼び出すとクッキーはスタックに配置され、関数の終了時に、スタックの値がグローバルなクッキーと比較されます。  違いが発見された場合は、バッファー オーバーランが発生したことを意味し、プログラムは直ちに終了します。  
  
 エラー R6035 は、保護された関数の呼び出し後に `__security_init_cookie` が呼び出されたことを示します。  実行を継続すると、スタック上のクッキーがグローバルなクッキーと一致しなくなるため、実際には発生していないバッファー オーバーランが検出されます。  
  
 次の DLL の例を考えます。  DLL のエントリ ポイントは、リンカーの [\/ENTRY \(エントリ ポイント シンボル\)](../../build/reference/entry-entry-point-symbol.md) オプションによって DllEntryPoint に設定されます。  これにより、通常はグローバル セキュリティ クッキーを初期化する CRT の初期化が省略されるため、DLL 自体で `__security_init_cookie` を呼び出す必要があります。  
  
```  
// Wrong way to call __security_init_cookie  
DllEntryPoint(...) {  
   DllInitialize();  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
  
void DllInitialize() {  
   __security_init_cookie();  
}  
```  
  
 この例では、エラー R6035 が生成されます。これは、DllEntryPoint が構造化例外処理を使用するため、バッファー オーバーランの検出にセキュリティ クッキーを使用するからです。  DllInitialize が呼び出されるときには、グローバル セキュリティ クッキーは既にスタックに配置されています。  
  
 正しい方法については、次の例で説明します。  
  
```  
// Correct way to call __security_init_cookie  
DllEntryPoint(...) {  
   __security_init_cookie();  
   DllEntryHelper();  
}  
  
void DllEntryHelper() {  
   ...  
   __try {  
      ...  
   } __except()... {  
      ...  
   }  
}  
```  
  
 この例では、DllEntryPoint はバッファー オーバーランに対して保護されていない \(ローカルの文字列バッファーを含まず、構造化例外処理を使用しない\) ため、`__security_init_cookie` を安全に呼び出すことができます。  その後、保護されているヘルパー関数を呼び出します。  
  
> [!NOTE]
>  R6035 エラー メッセージが生成されるのは、x86 のデバッグ CRT、構造化例外処理の場合のみです。しかし、すべてのプラットフォーム、すべての形式で \(C\+\+ EH など\) エラー条件は成立しています。  
  
## 参照  
 [コンパイラ セキュリティの徹底調査](http://go.microsoft.com/fwlink/?linkid=7260)