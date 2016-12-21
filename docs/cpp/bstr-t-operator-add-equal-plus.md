---
title: "_bstr_t::operator +=、+ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_bstr_t::operator+"
  - "_bstr_t::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "+ 演算子, _bstr_t オブジェクト"
  - "+= 演算子, 追加 (文字列を)"
ms.assetid: d28316ce-c2c8-4a38-bdb3-44fa4e582c44
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _bstr_t::operator +=、+
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_bstr_t` オブジェクトの末尾に文字を追加するか、2 つの文字列を連結します。  
  
## 構文  
  
```  
  
      _bstr_t& operator+=(  
   const _bstr_t& s1   
);  
_bstr_t operator+(  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const char* s2,  
   const _bstr_t& s1   
);  
friend _bstr_t operator+(  
   const wchar_t* s3,  
   const _bstr_t& s1   
);  
```  
  
#### パラメーター  
 *s1*  
 `_bstr_t` オブジェクト。  
  
 *s2*  
 マルチバイト文字列。  
  
 `s3`  
 Unicode 文字列。  
  
## 解説  
 これらの演算子は文字列連結を実行します。  
  
-   **operator\+\=\(**  *s1*  **\)** このオブジェクトのカプセル化された `BSTR` の末尾に、*s1* のカプセル化された `BSTR` の文字を追加します。  
  
-   **operator\+\(**  *s1*  **\)** このオブジェクトの `BSTR` を *s1* に連結することによって作成される、新しい `_bstr_t` を返します。  
  
-   **operator\+\(**  *s2*  **&#124;**  *s1*  **\)** Unicode に変換されたマルチバイト文字列 *s2* を *s1* 内にカプセル化された `BSTR` と連結することによって作成される、新しい `_bstr_t` を返します。  
  
-   **operator\+\(**  `s3` **,**  *s1*  **\)** *s1* にカプセル化された `BSTR` に Unicode 文字列 `s3` を連結することによって作成される、新しい `_bstr_t` を返します。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_bstr\_t クラス](../cpp/bstr-t-class.md)