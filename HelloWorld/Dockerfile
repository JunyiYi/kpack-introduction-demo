FROM mcr.microsoft.com/dotnet/sdk:5.0-buster-slim AS builder

WORKDIR /s
COPY Program.cs HelloWorld.csproj ./
RUN dotnet build -c Release


FROM mcr.microsoft.com/dotnet/runtime:5.0-buster-slim AS runtime

WORKDIR /app
COPY --from=builder /s/bin/Release/net5.0 .
ENTRYPOINT [ "./HelloWorld" ]
