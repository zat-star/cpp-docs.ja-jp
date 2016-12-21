---
title: "方法: Windows レジストリにデータを書き込む (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "レジストリ, 書き込み"
  - "Visual C++, 書き込み (Windows レジストリに)"
ms.assetid: 3d40b978-4baa-4779-bfe3-47e2917b757f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows レジストリにデータを書き込む (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:Microsoft.Win32.Registry.CurrentUser> キーを使用して、**Software** キーに対応する <xref:Microsoft.Win32.RegistryKey> クラスの書き込み可能インスタンスを作成する方法を次のコード例に示します。  その後、<xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A> メソッドを使用して、新しいキーを作成し、キーと値のペアを追加します。  
  
## 例  
  
### コード  
  
```  
// registry_write.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main()  
{  
   // The second OpenSubKey argument indicates that  
   // the subkey should be writable.   
   RegistryKey^ rk;  
   rk  = Registry::CurrentUser->OpenSubKey("Software", true);  
   if (!rk)  
   {  
      Console::WriteLine("Failed to open CurrentUser/Software key");  
      return -1;  
   }  
  
   RegistryKey^ nk = rk->CreateSubKey("NewRegKey");  
   if (!nk)  
   {  
      Console::WriteLine("Failed to create 'NewRegKey'");  
      return -1;  
   }  
  
   String^ newValue = "NewValue";  
   try  
   {  
      nk->SetValue("NewKey", newValue);  
      nk->SetValue("NewKey2", 44);  
   }  
   catch (Exception^)  
   {  
      Console::WriteLine("Failed to set new values in 'NewRegKey'");  
      return -1;  
   }  
  
   Console::WriteLine("New key created.");  
   Console::Write("Use REGEDIT.EXE to verify ");  
   Console::WriteLine("'CURRENTUSER/Software/NewRegKey'\n");  
   return 0;  
}  
```  
  
## 解説  
 .NET Framework を使用すると、<xref:Microsoft.Win32.Registry> クラスと [RegistryKey](https://msdn.microsoft.com/en-us/library/microsoft.win32.registrykey.aspx) クラスを使用してレジストリにアクセスできます。この 2 つのクラスはどちらも <xref:Microsoft.Win32> 名前空間で定義されています。  **Registry** クラスは、<xref:Microsoft.Win32.RegistryKey> クラスの静的インスタンスのコンテナーです。  各インスタンスは、ルート レジストリ ノードを表します。  インスタンスは、<xref:Microsoft.Win32.Registry.ClassesRoot>、<xref:Microsoft.Win32.Registry.CurrentConfig>、<xref:Microsoft.Win32.Registry.CurrentUser>、<xref:Microsoft.Win32.Registry.LocalMachine>、および <xref:Microsoft.Win32.Registry.Users> です。  
  
## 参照  
 [方法: Windows レジストリからデータを読み込む](../dotnet/how-to-read-data-from-the-windows-registry-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)