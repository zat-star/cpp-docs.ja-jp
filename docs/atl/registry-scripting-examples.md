---
title: "レジストリのスクリプトの例 | Microsoft Docs"
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
  - "レジストラー スクリプト [ATL]"
  - "レジストリ, レジストラー"
  - "スクリプト, 例"
  - "スクリプト, レジストラー スクリプト"
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# レジストリのスクリプトの例
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このトピックのスクリプト例では、システム レジストリにキーを追加する方法と、レジストラー COM サーバーを登録し、複数のパース ツリーを指定します。  
  
## HKEY\_CURRENT\_USER にキーを追加します。  
 次のパース ツリーはシステム レジストリにキーを一つ追加する簡単なスクリプトについて説明します。  特に、スクリプトは `HKEY_CURRENT_USER`に、キー `MyVeryOwnKey`を追加します。  また、新しいキーに `HowGoesIt?` 既定の文字列値を割り当てます:  
  
```  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
 このスクリプトは、次のように複数のサブキーを定義するために簡単に拡張できます:  
  
```  
HKCU  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
   {  
      'HasASubkey'  
      {  
         'PrettyCool?' = d '55'  
         val 'ANameValue' = s 'WithANamedValue'  
      }  
   }  
}  
```  
  
 これで、スクリプトは `MyVeryOwnKey`に、サブキー `HasASubkey`を追加します。  このサブキーに、`PrettyCool?` のサブキー \(55 の既定の `DWORD` 値を使用\) という `ANameValue` 両方の値を追加します \( `WithANamedValue`の文字列値\)。  
  
##  <a name="_atl_register_the_registrar_com_server"></a> レジストラー COM サーバーを登録します。  
 次のスクリプト レジストラー COM サーバー自体を登録します。  
  
```  
HKCR  
{  
   ATL.Registrar = s 'ATL Registrar Class'  
   {  
      CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
   }  
   NoRemove CLSID  
   {  
      ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} =  
                   s 'ATL Registrar Class'  
      {  
         ProgID = s 'ATL.Registrar'  
         InprocServer32 = s '%MODULE%'  
         {  
            val ThreadingModel = s 'Apartment'  
         }  
      }  
   }  
}  
```  
  
 実行時には、このパース ツリーは `HKEY_CLASSES_ROOT`に `ATL.Registrar` のキーを追加します。  この新しいキーに、と:  
  
-   `ATL Registrar Class` を、キーの既定の文字列値指定します。  
  
-   サブキーとして `CLSID` を追加します。  
  
-   `CLSID`に `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` を指定します。  \(この値は `CoCreateInstance`で使用するレジストラーの CLSID\) です。  
  
 `CLSID` が共有されるため、登録解除モードで削除しないでください。  ステートメントは、`NoRemove CLSID``CLSID` が登録解除モードの登録のモードで開き、無視することを示すことによって、これを行います。  
  
 `ForceRemove` のステートメントでは、キーを再作成する前にキーとサブキーをすべて削除して、ハウスキーピング関数を提供します。  これは、サブキーの名前が変更された場合に便利です。  このスクリプト例では `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` が既に存在する場合は、`ForceRemove` 確認します。  これは、`ForceRemove`:  
  
-   再帰的に `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` とサブキーをすべて削除します。  
  
-   `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`を再作成します。  
  
-   `ATL Registrar Class` をように `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`の既定の文字列値追加します。  
  
 パース ツリーは 2 `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`に、新しいサブキーを追加します。  最初のキー、`ProgID`は、ProgID である既定の文字列値を取得します。  2 番目のキー、`InprocServer32`は、セクションで説明するプリプロセッサの値である既定の文字列値、`%MODULE%`、この記事の [を使用して置き換え可能パラメーター \(レジストラー プリプロセッサ\)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)取得します。  `InprocServer32` は、名前付きの値、`Apartment`の文字列値を持つ `ThreadingModel`を取得します。  
  
## 複数のパース ツリーを指定します。  
 スクリプトで複数のパース ツリーを指定するには、別の最後に 1 個のツリーを単純に設定します。  たとえば、次のスクリプトは `HKEY_CLASSES_ROOT` と `HKEY_CURRENT_USER`両方のパース ツリーに、`MyVeryOwnKey`キーを追加します:  
  
```  
HKCR  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
HKEY_CURRENT_USER  
{  
   'MyVeryOwnKey' = s 'HowGoesIt?'  
}  
```  
  
> [!NOTE]
>  レジストラー スクリプトでは、KB は、最大のトークンのサイズです。  \(トークンは、構文を認識可能な要素です。前スクリプトの例では、`HKCR`、`HKEY_CURRENT_USER`、`'MyVeryOwnKey'`と `'HowGoesIt?'` は、すべてのトークンです。  
  
## 参照  
 [レジストラー スクリプトの作成](../Topic/Creating%20Registrar%20Scripts.md)