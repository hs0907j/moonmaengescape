# 문맹탈출 - Capstone1 Project  
#              made by. 정환성, 김현우, 조규진
# 1. 목차  
1. [목차](#1---)
2. [Translation PRJ](#2-translation-prj)  
2.1. [Dependency](#21-dependency)  
2.2. [Usage](#22-usage)  
2.3. [ETC](#23-etc)  
3. [OCR PRJ](#3-ocr-prj)  
3.1. [Dependency](#31-dependency)  
3.2. [Usage](#32-usage)  
3.3. [ETC](#33-etc)  

# 2. Translation PRJ
> # 2.1. Dependency
> * 언어 : `CPP`  
> * 사용 라이브러리 : `Curl`, `rapidJSON`  
>  
> # 2.2. Usage
> * __Class name__
>   * `translator`  
> * __Visible function__ 
>   * `void` `translate` (`char*`, `int`, `const char*`)
>
> ```
> translator TR;    //declare class
> char* source;     //set your own text at here
> char* result[BUF_SIZE];     //results will be stored here.
> 
> TR.translate (result, BUF_SIZE, (const char*)source);
>
> if (result == NULL)
>   //ERROR
> else
>   //TODO
> ```
> # 2.3 ETC
> * 번역 부분 개발은 종료되었습니다.
> * 다음 패키지의 install이 필요합니다.
> ```
> $ sudo apt-get install libcurl4-openssl-dev



# 3. OCR PRJ
> # 3.1. Dependency
> * 언어 : `CPP`, `Python`  
> * 특이사항 : CPP상에서 Embedded Python이 사용되었습니다.  
>  
> # 3.2. Usage
> * __Class name__
>   * `ocr_vision`  
> * __Visible function__ 
>   * `void` `detect_text` (`char*`, `int`, `const char*`, `const char*`)
>
> ```
> ocr_vision OCR;           //declare class
> char result[BUF_SIZE];    //results will be stored here.
> char *imgpath;            //target image filepath.
>
> //'ocr' is python file's name
> OCR.detect_text ( result, BUF_SIZE, imgpath, "ocr" );
>
> if(result == NULL)
>   //ERROR
> else
>   //TODO
> ```
> # 3.3 ETC
> * 결과로 얻은 텍스트의 위치에 해당하는 좌표는 아직 얻어오지 못합니다.
> * 빌드 / 실행에 파이썬이 요구되며, 특히 빌드 이후 실행시 실행 파일과 파이썬 코드가 모두 존재해야 실행이 가능합니다.  
> * 다음 패키지의 install이 필요합니다.
> ```
> $ sudo apt-get install python-dev
> ```
> * 빌드시 헤더 파일을 찾지 못할 경우 (include path 지정이 작동하지 않을 때, 비추천)
> ```
> $ sudo cp /usr/include/python2.7/*.h /usr/include/
> ```
> * 실행시 다음 에러가 출력될 때
> ```
> > ImportError: No module named google.cloud
> 
> $ sudo apt-get install python-pip
> $ pip install --upgrade google-api-python-client
> $ sudo python -m pip install google-cloud
> 
> > 이후 gcloud init 등을 통해 환경 설정 이후 재실행
> ```
> 
