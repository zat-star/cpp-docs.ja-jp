---
title: "方法: Windows レジストリからデータを読み込む (C++/CLI) | Microsoft Docs"
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
  - "レジストリ, 読み取り"
  - "Visual C++, 読み取り (Windows レジストリから)"
ms.assetid: aebf52c0-acc7-40e2-adbc-d34e0a1e467e
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 方法: Windows レジストリからデータを読み込む (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

<xref:Microsoft.Win32.Registry.CurrentUser> キーを使用して、Windows レジストリからデータを読み込む方法を次のコード例に示します。  まず、<xref:Microsoft.Win32.RegistryKey.GetSubKeyNames%2A> メソッドを使用してサブキーを一覧表示し、次に、<xref:Microsoft.Win32.RegistryKey.OpenSubKey%2A> メソッドを使用して Identities サブキーを開きます。  ルート キー同様、各サブキーは <xref:Microsoft.Win32.RegistryKey> クラスで表されます。  最後に、新しい <xref:Microsoft.Win32.RegistryKey> オブジェクトを使用してキーと値のペアが一覧表示されます。  
  
## 例  
  
### コード  
  
```  
// registry_read.cpp  
// compile with: /clr  
using namespace System;  
using namespace Microsoft::Win32;  
  
int main( )  
{  
   array<String^>^ key = Registry::CurrentUser->GetSubKeyNames( );  
  
   Console::WriteLine("Subkeys within CurrentUser root key:");  
   for (int i=0; i<key->Length; i++)  
   {  
      Console::WriteLine("   {0}", key[i]);  
   }  
  
   Console::WriteLine("Opening subkey 'Identities'...");  
   RegistryKey^ rk = nullptr;  
   rk = Registry::CurrentUser->OpenSubKey("Identities");  
   if (rk==nullptr)  
   {  
      Console::WriteLine("Registry key not found - aborting");  
      return -1;  
   }  
  
   Console::WriteLine("Key/value pairs within 'Identities' key:");  
   array<String^>^ name = rk->GetValueNames( );  
   for (int i=0; i<name->Length; i++)  
   {  
      String^ value = rk->GetValue(name[i])->ToString();  
      Console::WriteLine("   {0} = {1}", name[i], value);  
   }  
  
   return 0;  
}  
```  
  
## 解説  
 <xref:Microsoft.Win32.Registry> クラスは、<xref:Microsoft.Win32.RegistryKey> の静的インスタンスの単なるコンテナーです。  各インスタンスは、ルート レジストリ ノードを表します。  インスタンスは、<xref:Microsoft.Win32.Registry.ClassesRoot>、<xref:Microsoft.Win32.Registry.CurrentConfig>、<xref:Microsoft.Win32.Registry.CurrentUser>、<xref:Microsoft.Win32.Registry.LocalMachine>、および <xref:Microsoft.Win32.Registry.Users> です。  
  
 <xref:Microsoft.Win32.Registry> クラスのオブジェクトは、静的オブジェクトであるだけでなく、読み取り専用です。  さらに、レジストリ オブジェクトのコンテンツにアクセスするために作成される <xref:Microsoft.Win32.RegistryKey> クラスのインスタンスも読み取り専用です。  この動作のオーバーライド例については、「[方法: Windows レジストリにデータを書き込む](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)」を参照してください。  
  
 <xref:Microsoft.Win32.Registry> クラスには、さらに <xref:Microsoft.Win32.Registry.DynData> と <xref:Microsoft.Win32.Registry.PerformanceData> の 2 つのオブジェクトがあります。  この 2 つのオブジェクトは両方とも <xref:Microsoft.Win32.RegistryKey> クラスのインスタンスです。  <xref:Microsoft.Win32.Registry.DynData> オブジェクトには動的レジストリ情報が含まれています。動的レジストリ情報は、Windows 98 および Windows Me でのみサポートされています。  <xref:Microsoft.Win32.Registry.PerformanceData> オブジェクトを使用すると、Windows パフォーマンス モニター システムを使用するアプリケーションのパフォーマンス カウンター情報にアクセスできます。  <xref:Microsoft.Win32.Registry.PerformanceData> ノードは、実際にはレジストリに格納されていない情報を表しているため、Regedit.exe を使って表示することはできません。  
  
## 参照  
 [方法: Windows レジストリにデータを書き込む](../dotnet/how-to-write-data-to-the-windows-registry-cpp-cli.md)   
 [Windows の操作](../dotnet/windows-operations-cpp-cli.md)   
 [C\+\+\/CLI による .NET プログラミング](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)