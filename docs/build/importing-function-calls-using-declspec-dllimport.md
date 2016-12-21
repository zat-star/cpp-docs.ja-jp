---
title: "__declspec(dllimport) を使った関数呼び出しのインポート | Microsoft Docs"
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
  - "__declspec"
  - "dllimport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec(dllimport) キーワード [C++]"
  - "dllimport 属性 [C++], 関数呼び出しのインポート"
  - "関数呼び出し [C++], インポート"
  - "インポート (関数呼び出しを) [C++]"
ms.assetid: 6b53c616-0c6d-419a-8e2a-d2fff20510b3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# __declspec(dllimport) を使った関数呼び出しのインポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のコード例は、**\_declspec\(dllimport\)** を使って DLL からアプリケーションに関数呼び出しをインポートする方法を示しています。  `func1` は **main** 関数を含む .exe ファイルとは別の DLL にある関数であるものとします。  
  
 **\_\_declspec\(dllimport\)** を使用しない場合のコードは、次のようになります。  
  
```  
int main(void)   
{  
   func1();  
}  
```  
  
 コンパイラは、次のようなコードを生成します。  
  
```  
call func1  
```  
  
 リンカーは、この呼び出しを次のように変換します。  
  
```  
call 0x4000000         ; The address of 'func1'.  
```  
  
 `func1` が別の DLL にある場合は、`func1` のアドレスを知る方法がないので、リンカーは `func1` を直接解決できません。  16 ビット環境では、リンカーはこのコードのアドレスを .exe ファイル内のリストに追加します。ローダーは実行時にコードの正しいアドレスを追加します。  32 ビット環境および 64 ビット環境では、リンカーはコードのアドレスを通知するサンクを生成します。  32 ビット環境におけるサンクの例を次に示します。  
  
```  
0x40000000:    jmp DWORD PTR __imp_func1  
```  
  
 ここで、`imp_func1` は、.exe ファイルのインポート アドレス テーブル内にある `func1` のスロット用アドレスです。  このため、すべてのアドレスがリンカーに認識されます。  ローダーの役割は、読み込み時に .exe ファイルのインポート アドレス テーブルを更新して、すべてが正しく動作する状態を保つことです。  
  
 したがって、リンカーは不要なサンクを生成しないので、**\_\_declspec\(dllimport\)** を使用することをお勧めします。  サンクを使うとコードが大きくなり \(RISC システム上では、複数の命令になることもあります\)、キャッシュ パフォーマンスが低下する場合があります。  関数が DLL 内にあることをコンパイラに通知すると、間接呼び出しが自動的に生成されます。  
  
 コードは次のようになります。  
  
```  
__declspec(dllimport) void func1(void);  
int main(void)   
{  
   func1();  
}  
```  
  
 次の命令が生成されます。  
  
```  
call DWORD PTR __imp_func1  
```  
  
 サンクおよび `jmp` 命令がないので、コードは小さく高速になります。  
  
 DLL 内部で関数を呼び出す場合は、間接呼び出しを使用する必要はありません。  関数のアドレスは、既にわかっています。  間接呼び出しの前に関数のアドレスの読み込みと格納を行うには、時間と領域が必要になるため、直接呼び出しの方が高速でコンパクトです。  **\_\_declspec\(dllimport\)** を使用するのは、DLL の外部から DLL 関数を呼び出すときだけです。  DLL のビルド時に、DLL 内部の関数で **\_\_declspec\(dllimport\)** を使用しないでください。  
  
## 参照  
 [アプリケーションへのインポート](../build/importing-into-an-application.md)