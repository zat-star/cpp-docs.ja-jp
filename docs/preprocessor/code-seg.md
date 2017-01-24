---
title: "code_seg | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "code_seg_CPP"
  - "vc-pragma.code_seg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "code_seg プラグマ"
  - "プラグマ, code_seg"
ms.assetid: bf4faac1-a511-46a6-8d9e-456851d97d56
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# code_seg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

関数が格納される .obj ファイル内のテキスト セグメントを指定します。  
  
## 構文  
  
```  
#pragma code_seg( [ [ { push | pop }, ] [ identifier, ] ] [ "segment-name" [, "segment-class" ] )  
```  
  
## 解説  
 `code_seg` プラグマ ディレクティブは、インスタンス化されたテンプレート用に生成されたオブジェクト コードや、コンパイラによって暗黙的に生成されたコード \(特殊なメンバー関数など\) の格納場所を制御するものではありません。  代わりに、[\_\_declspec\(code\_seg\(...\)\)](../cpp/code-seg-declspec.md) 属性を使用することをお勧めします。すべてのオブジェクト コードの格納場所も、  コンパイラによって生成されたコードの格納場所も制御できるためです。  
  
 .obj ファイル内の*セグメント*は、メモリへの読み込み単位となる名前付きのデータ ブロックです。  *テキスト セグメント*は、実行可能なコードが格納されるセグメントです。  この記事では、*セグメント*と*セクション*という用語は同義です。  
  
 `code_seg` プラグマ ディレクティブは、翻訳単位の後続のすべてのオブジェクト コードを `segment-name` というテキスト セグメントに格納するように、コンパイラに指示します。  既定では、.obj ファイル内の関数に使用されるテキスト セグメントには .text という名前が付けられます。  
  
 `code_seg` プラグマ ディレクティブは、パラメーターが指定されない場合、後続のオブジェクト コードのテキスト セグメント名を .text にリセットします。  
  
 **Push** \(省略可能\)  
 レコードを内部コンパイラ スタックに格納します。  **push** には `identifier` と `segment-name` を指定できます。  
  
 **pop** \(省略可能\)  
 内部コンパイラ スタックの最上部からレコードを削除します。  
  
 `identifier` \(省略可能\)  
 **push** と共に使用した場合、内部コンパイラ スタックのレコードに名前を割り当てます。  **pop** と共に使用した場合、`identifier` が削除されるまでレコードを内部スタックからポップします。`identifier` が内部スタックにない場合は何もポップされません。  
  
 `identifier` を使用して、複数のレコードを 1 つの **pop** コマンドでポップできます。  
  
 "`segment-name`" \(省略可能\)  
 引数の名前。  **pop** と共に使用した場合、スタックがポップされ、`segment-name` がアクティブなテキスト セグメント名になります。  
  
 "`segment-class`" \(省略可能\)  
 無視されますが、C\+\+ 2.0 より前のバージョンとの互換性を保つために残されています。  
  
 [DUMPBIN.EXE](../build/reference/dumpbin-command-line.md) アプリケーションを使用して .obj ファイルを表示できます。  サポートされている各ターゲット アーキテクチャの DUMPBIN のバージョンは [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] に付属しています。  
  
## 使用例  
 この例では、`code_seg` プラグマ ディレクティブを使用して、オブジェクト コードの格納場所を制御する方法を示しています。  
  
```  
// pragma_directive_code_seg.cpp  
void func1() {                  // stored in .text  
}  
  
#pragma code_seg(".my_data1")  
void func2() {                  // stored in my_data1  
}  
  
#pragma code_seg(push, r1, ".my_data2")  
void func3() {                  // stored in my_data2  
}  
  
#pragma code_seg(pop, r1)      // stored in my_data1  
void func4() {  
}  
  
int main() {  
}  
```  
  
 セクションを作成する場合に使用しない名前のリストについては、「[\/SECTION](../build/reference/section-specify-section-attributes.md)」を参照してください。  
  
 初期化されたデータのセクション \([data\_seg](../preprocessor/data-seg.md)\)、初期化されていないデータのセクション \([bss\_seg](../preprocessor/bss-seg.md)\)、および const 変数のセクション \([const\_seg](../preprocessor/const-seg.md)\) を指定することもできます。  
  
## 参照  
 [code\_seg \(\_\_declspec\)](../cpp/code-seg-declspec.md)   
 [プラグマ ディレクティブと \_\_Pragma キーワード](../preprocessor/pragma-directives-and-the-pragma-keyword.md)