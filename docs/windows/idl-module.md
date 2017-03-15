---
title: "idl_module | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc-attr.idl_module"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "idl_module attribute"
ms.assetid: 3578b337-e38a-4334-b747-15404c02dbc0
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# idl_module
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

.dll ファイルのエントリ ポイントを指定します。  
  
## 構文  
  
```  
  
      [ idl_module (   
   name=module_name,   
   dllname=dll,   
   uuid="uuid",   
   helpstring="help text",   
   helpstringcontext=helpcontextID,   
   helpcontext=helpcontext,   
   hidden,   
   restricted  
) ]  
function declaration  
```  
  
#### パラメーター  
 **name**  
 .idl ファイルに含まれるコード ブロックのユーザー定義名。  
  
 **dllname** \(省略可能\)  
 .dll ファイルのエクスポートを含む。  
  
 `uuid` \(省略可能\)  
 一意の ID。  
  
 **helpstring\(I\)** \(省略可能\)  
 タイプ ライブラリを表すために使用される文字列。  
  
 **helpstringcontext** \(省略可能\)  
 .hlp または .chm ファイルのヘルプ トピックの ID。  
  
 **helpcontext\(X\)** \(省略可能\)  
 このタイプ ライブラリのヘルプ ID。  
  
 **hidden\(E\)** \(省略可能\)  
 ライブラリが表示されないようにするパラメーター。  詳細については[hidden\(E\)](http://msdn.microsoft.com/library/windows/desktop/aa366861) の MIDL の属性を参照してください。  
  
 ***restricted***  \(省略可能\)  
 ライブラリのメンバーは任意に呼び出すことはできません。  詳細については[restricted](http://msdn.microsoft.com/library/windows/desktop/aa367157) の MIDL の属性を参照してください。  
  
 *関数宣言*  
 ユーザーが定義する関数。  
  
## 解説  
 `idl_module` C\+\+ 属性は .dll ファイルからインポートする .dll ファイルのエントリ ポイントを指定することができます。  
  
 **idl\_module**  の属性に [モジュール](http://msdn.microsoft.com/library/windows/desktop/aa367099) の MIDL の属性と同様の機能があります。  
  
 .dll ファイルから.idl ファイルのライブラリ ブロックに DLL のエントリ ポイントを指定することでエクスポートできる COM オブジェクトから何もエクスポートできます。  
  
 2 ステップの先頭に使用 `idl_module`。  まずname\/DLL のペアを定義する必要があります。  その後エントリ ポイントを指定するために `idl_module` を使用すると名前とそのほかの属性を指定します。  
  
## 使用例  
 次のコードは `idl_module` 属性の使用方法を示します :  
  
```  
// cpp_attr_ref_idl_module.cpp  
// compile with: /LD  
[idl_quote("midl_pragma warning(disable:2461)")];  
[module(name="MyLibrary"), idl_module(name="MyLib", dllname="xxx.dll")];  
[idl_module(name="MyLib"), entry(4), usesgetlasterror]  
void FuncName(int i);  
```  
  
## 必要条件  
  
### 属性コンテキスト  
  
|||  
|-|-|  
|**対象**|任意|  
|**複数回の適用**|Ｘ|  
|**必要な属性**|なし|  
|**無効な属性**|なし|  
  
 詳細については[属性コンテキスト](../windows/attribute-contexts.md) を参照してください。  
  
## 参照  
 [IDL Attributes](../windows/idl-attributes.md)   
 [Stand\-Alone Attributes](../Topic/Stand-Alone%20Attributes.md)   
 [entry](../windows/entry.md)   
 [Attributes Samples](http://msdn.microsoft.com/ja-jp/558ebdb2-082f-44dc-b442-d8d33bf7bdb8)