FUNCTION dot_product  
INPUT:  
    v1: INTEGER ARRAY  // Passed by value  
    v2: INTEGER ARRAY  // Passed by value  
RETURNS: INTEGER  
BEGIN  
    product := 0  
    FOR i FROM 0 TO LENGTH(v1) - 1 DO  
        product := product + (v1[i] * v2[i])  
    END_FOR  
    RETURN product  
END  

// Algorithm to Check Orthogonality with Function  
ALGORITHM CheckOrthogonal  
INPUT:  
    VectorPairs: LIST OF (v1: INTEGER ARRAY, v2: INTEGER ARRAY)  
OUTPUT:  
    Results: BOOLEAN ARRAY  

BEGIN  
    Results := EMPTY_LIST  
    FOR EACH pair IN VectorPairs DO  
        product := dot_product(pair.v1, pair.v2)  
        Results.APPEND(product = 0)  
    END_FOR  
    RETURN Results  
END  
