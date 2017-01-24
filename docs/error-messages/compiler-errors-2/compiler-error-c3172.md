---
title: "コンパイラ エラー C3172 | Microsoft Docs"
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
  - "C3172"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3172"
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3172
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module\_name': プロジェクト内で異なる idl\_module の属性を指定することはできません。  
  
 コンパイル中に、2 つのファイルで異なる `dllname` パラメーターまたは `version` パラメーターを持つ、同名の [idl\_module](../../windows/idl-module.md) 属性が見つかりました。  一意の `idl_module` 属性は、コンパイルごとに 1 つだけ指定できます。  
  
 複数のソース コード ファイルでは同じ `idl_module` 属性を指定できます。  
  
 たとえば、次の `idl_module` 属性が見つかったとします。  
  
```  
// C3172.cpp  
[module(name="MyMod")];  
[ idl_module(name="x", dllname="file.dll", version="1.1") ];  
int main() {}  
```  
  
 次に、以下のコードを実行します。  
  
```  
// C3172b.cpp  
// compile with: C3172.cpp  
// C3172 expected  
[ idl_module(name="x", dllname="file.dll", version="1.0") ];  
```  
  
 この場合は C3172 エラーになります。バージョンの値が異なることに注意してください。