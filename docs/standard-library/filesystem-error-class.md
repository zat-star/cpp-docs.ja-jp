---
title: "filesystem_error クラス | Microsoft Docs"
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
  - "filesystem/std::tr2::sys::filesystem_error"
dev_langs: 
  - "C++"
ms.assetid: c53aac27-c1fa-43e4-8967-48ea8ba1f172
caps.latest.revision: 13
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# filesystem_error クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

低レベル システム オーバーフローをレポートするためにスローされるすべての例外のための基底クラス。  
  
## 構文  
  
```  
class filesystem_error    : public system_error;  
```  
  
## 解説  
 このクラスは、\<filesystem\> 関数のエラーを報告するためにスローされる例外すべてに対する基底クラスとして機能します。 このクラスは、文字列型のオブジェクトを格納します。ここでは説明をわかりやすくするために、このオブジェクトを mymesg と呼ぶことにします。 さらに、このクラスは path 型のオブジェクトを 2 つ格納します。ここでは、これらのオブジェクトを mypval1 および mypval2 と呼ぶことにします。  
  
## filesystem\_error::filesystem\_error  
  
```  
filesystem_error(const string& what_arg, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, error_code ec);  
filesystem_error(const string& what_arg,  
    const path& pval1, const path& pval2, error_code ec);  
```  
  
 最初のコンストラクターは、what\_arg と ec からメッセージを構築します。 2 番目のコンストラクターは、mypval1 に格納するメッセージを pval1 から構築します。 3 番目のコンストラクターは、mypval1 に格納するメッセージを pval1 から構築して、mypval2 に格納するメッセージを pval2 から構築します。  
  
## filesystem\_error::path1  
  
```  
const path& path1() const noexcept;  
  
```  
  
 このメンバー関数は、mypval1 を返します。  
  
## filesystem\_error::path2  
  
```  
const path& path2() const noexcept;  
  
```  
  
 このメンバー関数は、mypval2 を返します。  
  
## filesystem\_error::what  
  
```  
const char *what() const noexcept;  
```  
  
 このメンバー関数は、NTBS へのポインターを返します。この NTBS は、可能であればruntime\_error::what\(\)、system\_error::what\(\)、mymesg、mypval1.native\_string\(\)、および mypval2.native\_string\(\) から構成されます。  
  
## 必要条件  
 **ヘッダー:** filesystem  
  
 **名前空間:** std::tr2::sys  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [system\_error クラス](../standard-library/system-error-class.md)   
 [\<filesystem\>](../Topic/%3Cfilesystem%3E.md)   
 [\<exception\>](../standard-library/exception.md)