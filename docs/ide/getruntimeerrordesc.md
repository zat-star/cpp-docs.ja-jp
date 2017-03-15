---
title: "GetRuntimeErrorDesc | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetRuntimeErrorDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConversionError メソッド"
  - "GetRuntimeErrorDesc メソッド"
  - "RangeError メソッド"
  - "ReferenceError メソッド"
  - "RegExpError メソッド"
  - "SyntaxError メソッド"
  - "TypeError メソッド"
  - "URIError メソッド"
ms.assetid: d56fdd2e-6ad0-4c49-9e98-bcf0105e1b12
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# GetRuntimeErrorDesc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

例外の種類の説明を返します。  
  
## 構文  
  
```  
  
      function GetRuntimeErrorDesc(   
   strRuntimeErrorName    
);  
```  
  
#### パラメーター  
 *strRuntimeErrorName*  
 発生した例外の種類の名前。  
  
## 戻り値  
 例外の種類の説明を返します。  
  
## 解説  
 例外の種類の説明を返します。  例外の種類は次のいずれかです。  
  
|例外の種類|Description|  
|-----------|-----------------|  
|ConversionError|変換できないオブジェクトの変換を試みるたびに発生します。|  
|RangeError|有効範囲外の引数が関数に指定された場合に発生します。  たとえば、有効な正の整数でない長さの `Array` オブジェクトを作成しようとすると、このエラーが発生します。|  
|ReferenceError|無効な参照が検出された場合に発生します。  たとえば、予測した参照が null である場合などです。|  
|RegExpError|正規表現でコンパイル エラーがあったときに発生します。  正規表現がコンパイルされると、このエラーは発生しません。  たとえば、正規表現のパターンを宣言するときの構文が無効である場合や、フラグが *i*、*g*、および *m* 以外である場合、または同じフラグが複数個含まれる場合などに、このエラーが発生します。|  
|SyntaxError|ソース テキストが解析され、そのテキストの構文が間違っている場合に発生します。  たとえば、`eval` 関数の呼び出しで無効なプログラム テキストを引数として指定したときに、このエラーが発生します。|  
|TypeError|オペランドの実際の型が予測した型と一致しないと常に発生します。  たとえば、関数の呼び出し対象がオブジェクトではない場合や、その呼び出しをサポートしていない場合にこのエラーが発生します。|  
|URIError|無効な URI \(Uniform Resource Indicator\) が検出されたときに発生します。  たとえば、エンコードまたはデコードされている文字列に無効な文字が見つかると、このエラーが発生します。|  
  
## 参照  
 [共通の JScript 関数による C\+\+ ウィザードのカスタマイズ](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [C\+\+ ウィザードの JScript 関数](../ide/jscript-functions-for-cpp-wizards.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)