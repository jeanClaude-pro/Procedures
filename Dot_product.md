PROCEDURE dot_product  
INPUT:  
    v1: INTEGER ARRAY  // Passed by value  
    v2: INTEGER ARRAY  // Passed by value  
    ps: INTEGER        // Passed by reference (output parameter)  
BEGIN  
    ps := 0  
    FOR i FROM 0 TO LENGTH(v1) - 1 DO  
        ps := ps + (v1[i] * v2[i])  
    END_FOR  
END  

// Algorithm to Check Orthogonality for n Pairs  
ALGORITHM CheckOrthogonal  
INPUT:  
    VectorPairs: LIST OF (v1: INTEGER ARRAY, v2: INTEGER ARRAY)  
OUTPUT:  
    Results: BOOLEAN ARRAY  

BEGIN  
    Results := EMPTY_LIST  
    FOR EACH pair IN VectorPairs DO  
        ps := 0  
        dot_product(pair.v1, pair.v2, ps)  // ps is updated by reference  
        Results.APPEND(ps = 0)  
    END_FOR  
    RETURN Results  
END  
