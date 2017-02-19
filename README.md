#include <iostream>
#include <stdio.h>
#include <stdlib.h>
#define N 100

class Stack
{
    private:

    double data_[N];
    int size_;

    public:

    void Push(double value);
    int Pop();
    int Get();
    int Capacity();
    void Empty();
    int Size();
    void Print();
};

int main()
{
    Stack s;
    int i;
    s.Push(15);
    s.Push(14);
    printf("Capacity = %d\n", s.Capacity());
    printf("Size1 = %d\n", s.Size());
    printf("Print === ");
    s.Print();
    printf("Pop = %d\n", s.Pop());
    printf("Get = %d\n", s.Get());
    printf("Size2 = %d\n", s.Size());
    s.Empty();
    printf("Size3 = %d\n", s.Size());

    return 0;
}

void Stack::Push(double value)
{
    data_[size_++] = value;
}

int Stack::Pop()
{
    return data_[--size_];
}

int Stack::Get()
{
    int i = size_ - 1;
    return data_[i];
}

int Stack::Capacity()
{
    return N;
}

void Stack::Empty()
{
    size_ = 0;
}

int Stack::Size()
{
    return size_;
}

void Stack::Print()
{
    int i;
    if(size_ == 0)
    {
        printf("Stack is Empty");
    }
    else
    {
        i = size_ - 1;
        for(i; i>= 0; i--)
        {
            printf("%f ", data_[i]);
        }
        printf("\n");
    }
}
