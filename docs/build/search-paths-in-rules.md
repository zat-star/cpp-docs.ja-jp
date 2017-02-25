---
title: "規則の検索パス | Microsoft Docs"
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
  - "推論規則 (NMAKE の)"
  - "規則, 推論"
  - "検索パス (NMAKE の推論規則の)"
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# 規則の検索パス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

```  
{frompath}.fromext{topath}.toext:  
   commands  
```  
  
## 解説  
 依存関係で指定されたパスが推論規則のパスと正確に一致する場合だけ、推論規則が依存関係に適用されます。  依存ファイルのディレクトリは *frompath* で指定し、ターゲットのディレクトリは *topath* で指定します。空白を入れることはできません。  パスは、拡張子ごとに 1 つだけ指定します。  一方の拡張子でパスを指定した場合は、もう一方の拡張子でもパスを指定する必要があります。  現在のディレクトリを指定するには、ピリオド \(.\) または空の中かっこ \({ }\) を使用します。  マクロでは、*frompath* と *topath* を表すことができます。マクロは、プリプロセス時に呼び出されます。  
  
## 例  
  
### コード  
  
```  
{dbi\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUDBI) $<  
  
{ilstore\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{misc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{misc\}.c{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{msf\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
  
{bsc\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{mre\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{namesrvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $(YUPDB) $<  
  
{src\cvr\}.cpp{$(ODIR)}.obj::  
        $(CC) $(CFLAGS) $<  
```  
  
## 参照  
 [規則の定義](../build/defining-a-rule.md)