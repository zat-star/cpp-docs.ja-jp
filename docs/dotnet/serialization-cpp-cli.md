---
title: "シリアル化 (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".NET Framework [C++], シリアル化"
  - "マネージ コード [C++], シリアル化"
  - "NonSerializedAttribute クラス, マネージ アプリケーション"
  - "SerializableAttribute クラス, マネージ アプリケーション"
  - "シリアル化 [C++]"
  - "シリアル化 [C++], シリアル化の概要"
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# シリアル化 (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マネージ クラスのシリアル化 \(各フィールドまたはプロパティを含む\) は、<xref:System.SerializableAttribute> クラスと <xref:System.NonSerializedAttribute> クラスでサポートされます。シリアル化とは、オブジェクトまたはメンバーの状態を永続的なメディアに格納するプロセスです。  
  
## 解説  
 **SerializableAttribute** カスタム属性をマネージ クラスに適用してクラス全体をシリアル化するか、特定のフィールドまたはプロパティだけに適用してマネージ クラスの一部をシリアル化します。  マネージ クラスのフィールドまたはプロパティをシリアル化から除外するには **NonSerializedAttribute** カスタム属性を使用します。  
  
## 例  
  
### 説明  
 次の例では、`MyClass` クラス \(および `m_nCount` プロパティ\) がシリアル化可能としてマークされます。  ただし、`m_nData` プロパティは、**NonSerialized** カスタム属性で示されるようにシリアル化されません。  
  
### コード  
  
```  
// serialization_and_mcpp.cpp  
// compile with: /LD /clr  
using namespace System;  
  
[ Serializable ]  
public ref class MyClass {  
public:  
   int m_nCount;  
private:  
   [ NonSerialized ]  
   int m_nData;  
};  
```  
  
### コメント  
 両方の属性は、"短い形式の名前" \(**Serializable** および **NonSerialized**\) を使用して参照できます。  詳細については、「[属性の適用](../Topic/Applying%20Attributes.md)」で説明します。  
  
## 参照  
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)