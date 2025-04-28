ALGORITHM sumElements  
INPUT:  
    Array1: INTEGER ARRAY  
    Array2: INTEGER ARRAY  
OUTPUT:  
    Sum: INTEGER  

BEGIN  
    Sum := 0  

    // Check elements in Array1 not in Array2  
    FOR i FROM 0 TO LENGTH(Array1) - 1 DO  
        isPresent := FALSE  
        FOR j FROM 0 TO LENGTH(Array2) - 1 DO  
            IF Array1[i] = Array2[j] THEN  
                isPresent := TRUE  
                BREAK  
            END_IF  
        END_FOR  
        IF NOT isPresent THEN  
            Sum := Sum + Array1[i]  
        END_IF  
    END_FOR  

    // Check elements in Array2 not in Array1  
    FOR i FROM 0 TO LENGTH(Array2) - 1 DO  
        isPresent := FALSE  
        FOR j FROM 0 TO LENGTH(Array1) - 1 DO  
            IF Array2[i] = Array1[j] THEN  
                isPresent := TRUE  
                BREAK  
            END_IF  
        END_FOR  
        IF NOT isPresent THEN  
            Sum := Sum + Array2[i]  
        END_IF  
    END_FOR  

    RETURN Sum  
END  
