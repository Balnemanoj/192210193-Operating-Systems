#include <stdio.h>
#include <stdlib.h>
#define MAX_RECORDS 100
struct Record {
    int recordNumber;
    char data[50]; 
};
void writeRecord(struct Record *file, int *currentPosition, char newData[]) {
    if (*currentPosition < MAX_RECORDS) {
        struct Record newRecord;
        newRecord.recordNumber = *currentPosition + 1;
        snprintf(newRecord.data, sizeof(newRecord.data), "%s", newData);

        file[*currentPosition] = newRecord;
        (*currentPosition)++;
        printf("Record #%d written successfully.\n", newRecord.recordNumber);
    } else {
        printf("Error: File is full. Cannot write more records.\n");
    }
}
void readRecord(struct Record *file, int *currentPosition, int recordNumber) {
    if (recordNumber > 0 && recordNumber <= *currentPosition) {
        printf("Reading Record #%d: %s\n", recordNumber, file[recordNumber - 1].data);
    } else {
        printf("Error: Invalid record number or record not found.\n");
    }
}
void displayAllRecords(struct Record *file, int currentPosition) {
    printf("All Records in the File:\n");
    for (int i = 0; i < currentPosition; ++i) {
        printf("Record #%d: %s\n", file[i].recordNumber, file[i].data);
    }
}
int main() {
    struct Record file[MAX_RECORDS];
    int currentPosition = 0;
    writeRecord(file, &currentPosition, "Data for Record 1");
    writeRecord(file, &currentPosition, "Data for Record 2");
    writeRecord(file, &currentPosition, "Data for Record 3");
    readRecord(file, &currentPosition, 2);
    readRecord(file, &currentPosition, 1);
    displayAllRecords(file, currentPosition);
    return 0;
}
