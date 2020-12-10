# List-of-digits-returning-permutations
Given a number in the form of a list of digits, return all possible permutations.  For example, given [1,2,3], return [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]].


void permute(string a, int l, int r)  
{  
    // Base case  
    if (l == r)  
        cout<<a<<endl;  
    else
    {  
        // Permutations made  
        for (int i = l; i <= r; i++)  
        {  
  
            // Swapping done  
            swap(a[l], a[i]);  
  
            // Recursion called  
            permute(a, l+1, r);  
  
            //backtrack  
            swap(a[l], a[i]);  
        }  
    }  
}  
void perm(char a[], int level){

    static int flag[10] = {0};
    static char res[10];
    // If we are the last character of the input string 
    if(a[level] == '\0'){
        // First we assign stopping point to result
        res[level] = '\0';
        // Now we print everything
        for(int i = 0; res[i] != '\0'; ++i){
            printf("%c", res[i]);
        }
        printf("\n");
        ++counter;
    }
    else{
        // Scan the original string and flag to see what letters are available
        for(int i = 0; a[i] != '\0'; ++i){
            if(flag[i] == 0){
                res[level] = a[i];
                flag[i] = 1;
                perm(a, level + 1);
                flag[i] = 0;
            }
        }
    }
}

int main(){
    char first[] = "abc";
    perm(first, 0);
    return 0;
}
